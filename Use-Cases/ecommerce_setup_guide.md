# E-commerce Analytics Setup Guide

## Complete E-commerce Tracking Implementation

This comprehensive guide provides step-by-step implementation for tracking the entire e-commerce customer journey using Sealmetrics' privacy-first analytics platform.

## Core E-commerce Events

### 1. Basic Page View Tracking

**Implementation for all pages:**
```html
<script>
/* Basic E-commerce Page Tracking */
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'pageview',
   content_grouping: getEcommercePageType(),
   use_session: 1,
};

function getEcommercePageType() {
    const path = window.location.pathname;
    if (path.includes('/product/')) return 'product-pages';
    if (path.includes('/category/')) return 'category-pages';
    if (path.includes('/cart')) return 'cart-page';
    if (path.includes('/checkout')) return 'checkout-pages';
    if (path.includes('/account')) return 'account-pages';
    if (path === '/') return 'homepage';
    return 'general-pages';
}

var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### 2. Product View Tracking

**Implementation on product detail pages:**
```html
<script>
function trackProductView(productData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Product View',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           product_id: productData.id,
           product_name: productData.name,
           category: productData.category,
           subcategory: productData.subcategory,
           brand: productData.brand,
           price: productData.price,
           currency: productData.currency,
           availability: productData.inStock ? 'in_stock' : 'out_of_stock',
           
           // Product attributes
           color: productData.color,
           size: productData.size,
           material: productData.material,
           
           // Context
           traffic_source: getTrafficSource(),
           product_position: productData.listPosition,
           came_from_search: document.referrer.includes('search')
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Auto-track product views on page load
document.addEventListener('DOMContentLoaded', function() {
    if (window.productData) {
        trackProductView(window.productData);
    }
});
</script>
```

### 3. Add to Cart Tracking

**Implementation for add to cart buttons:**
```html
<button onclick="addToCart(productData)" class="add-to-cart-btn">Add to Cart</button>

<script>
function addToCart(product) {
    // Your add to cart logic here
    
    // Track the event
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Add to Cart',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           product_id: product.id,
           product_name: product.name,
           category: product.category,
           brand: product.brand,
           price: product.price,
           quantity: product.selectedQuantity || 1,
           
           // Selected variants
           selected_color: product.selectedColor,
           selected_size: product.selectedSize,
           
           // Cart context
           cart_total_items: getCartItemCount() + 1,
           cart_total_value: getCartTotal() + product.price,
           
           // User behavior
           time_on_product_page: getTimeOnPage(),
           images_viewed: getImagesViewed(),
           reviews_read: getReviewsRead()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### 4. Remove from Cart Tracking

```html
<script>
function removeFromCart(product) {
    // Your remove from cart logic here
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Remove from Cart',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           product_id: product.id,
           product_name: product.name,
           price: product.price,
           quantity_removed: product.quantity,
           removal_reason: product.removalReason, // 'price', 'changed_mind', 'found_better'
           
           // Cart state after removal
           cart_total_items: getCartItemCount() - product.quantity,
           cart_total_value: getCartTotal() - (product.price * product.quantity)
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### 5. Checkout Process Tracking

**Step 1: Checkout Started**
```html
<script>
function trackCheckoutStart(cartData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Checkout Started',
       value: cartData.totalValue,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           cart_total_items: cartData.totalItems,
           cart_total_value: cartData.totalValue,
           currency: cartData.currency,
           
           // Cart composition
           product_categories: cartData.categories,
           unique_products: cartData.uniqueProducts,
           average_item_value: cartData.totalValue / cartData.totalItems,
           
           // User context
           customer_type: cartData.customerType, // 'guest', 'registered', 'returning'
           has_account: cartData.hasAccount,
           
           // Session context
           session_duration: getSessionDuration(),
           pages_visited: getPagesVisited()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

**Step 2: Shipping Information**
```html
<script>
function trackShippingInfo(shippingData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Shipping Info Completed',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           shipping_method: shippingData.method, // 'standard', 'express', 'overnight'
           shipping_cost: shippingData.cost,
           delivery_estimate: shippingData.estimatedDays,
           
           // Address context (anonymized)
           shipping_country: shippingData.country,
           shipping_state: shippingData.state,
           shipping_city: shippingData.city,
           is_po_box: shippingData.isPoBox,
           
           // Checkout progress
           checkout_step: 2,
           time_on_checkout: getTimeOnCheckout()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

**Step 3: Payment Information**
```html
<script>
function trackPaymentInfo(paymentData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Payment Info Completed',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           payment_method: paymentData.method, // 'credit_card', 'paypal', 'apple_pay', 'google_pay'
           card_type: paymentData.cardType, // 'visa', 'mastercard', 'amex' (if applicable)
           
           // Checkout context
           checkout_step: 3,
           total_checkout_time: getTotalCheckoutTime(),
           
           // Security/Trust signals
           ssl_enabled: window.location.protocol === 'https:',
           trust_badges_shown: hasTrustBadges()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### 6. Purchase Completion Tracking

**Implementation on thank you/confirmation page:**
```html
<script>
function trackPurchase(orderData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'purchase',
       label: 'Purchase Completed',
       value: orderData.totalRevenue,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Order identification
           transaction_id: orderData.transactionId,
           order_number: orderData.orderNumber,
           
           // Revenue details
           subtotal: orderData.subtotal,
           tax_amount: orderData.taxAmount,
           shipping_cost: orderData.shippingCost,
           discount_amount: orderData.discountAmount,
           total_revenue: orderData.totalRevenue,
           currency: orderData.currency,
           
           // Order composition
           total_items: orderData.totalItems,
           unique_products: orderData.uniqueProducts,
           product_categories: orderData.categories,
           brands_purchased: orderData.brands,
           
           // Customer information
           customer_type: orderData.customerType, // 'new', 'returning'
           customer_lifetime_orders: orderData.lifetimeOrders,
           customer_lifetime_value: orderData.lifetimeValue,
           
           // Payment & Shipping
           payment_method: orderData.paymentMethod,
           shipping_method: orderData.shippingMethod,
           
           // Marketing attribution
           first_touch_source: orderData.firstTouchSource,
           last_touch_source: orderData.lastTouchSource,
           campaign: orderData.campaign,
           
           // Timing
           session_to_purchase_minutes: getSessionToPurchaseTime(),
           checkout_completion_time: getCheckoutCompletionTime(),
           
           // Promotions
           coupon_code: orderData.couponCode,
           promotion_name: orderData.promotionName,
           loyalty_points_used: orderData.loyaltyPointsUsed
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Auto-track purchase on thank you page
document.addEventListener('DOMContentLoaded', function() {
    if (window.orderData && window.location.pathname.includes('thank-you')) {
        trackPurchase(window.orderData);
    }
});
</script>
```

## Advanced E-commerce Tracking

### Wishlist/Save for Later Tracking

```html
<script>
function trackWishlistAdd(product) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Added to Wishlist',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           product_id: product.id,
           product_name: product.name,
           category: product.category,
           price: product.price,
           
           // Wishlist context
           wishlist_total_items: getWishlistCount() + 1,
           user_has_account: isLoggedIn(),
           
           // Engagement indicators
           time_considering: getTimeOnProduct(),
           alternative_products_viewed: getAlternativeProductsViewed()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Product Comparison Tracking

```html
<script>
function trackProductComparison(products) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Product Comparison',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           products_compared: products.length,
           product_ids: products.map(p => p.id),
           product_names: products.map(p => p.name),
           categories: [...new Set(products.map(p => p.category))],
           price_range_low: Math.min(...products.map(p => p.price)),
           price_range_high: Math.max(...products.map(p => p.price)),
           
           // Comparison context
           comparison_source: 'comparison_page', // or 'category_page', 'search_results'
           features_compared: getComparedFeatures()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Search Tracking

```html
<script>
function trackSiteSearch(searchData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Site Search',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           search_query: searchData.query,
           search_results_count: searchData.resultsCount,
           search_category: searchData.category,
           
           // Search quality
           has_results: searchData.resultsCount > 0,
           results_clicked: false, // Update when clicked
           
           // Search context
           search_source: searchData.source, // 'header', 'category_page', 'no_results_page'
           search_refinements: searchData.filters,
           sort_order: searchData.sortOrder
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## Platform-Specific Implementations

### Shopify Implementation

```html
<!-- Add to theme.liquid before closing </head> -->
<script>
// Shopify specific e-commerce tracking
{% if template contains 'product' %}
  window.productData = {
    id: {{ product.id }},
    name: {{ product.title | json }},
    category: {{ product.type | json }},
    brand: {{ product.vendor | json }},
    price: {{ product.price | money_without_currency | remove: ',' }},
    currency: {{ shop.currency }},
    inStock: {% if product.available %}true{% else %}false{% endif %},
    variants: {{ product.variants | json }}
  };
{% endif %}

{% if template contains 'cart' %}
  window.cartData = {
    totalItems: {{ cart.item_count }},
    totalValue: {{ cart.total_price | money_without_currency | remove: ',' }},
    currency: {{ shop.currency }},
    items: {{ cart.items | json }}
  };
{% endif %}

// Track Shopify checkout events
{% if first_time_accessed %}
  window.isNewCustomer = true;
{% endif %}
</script>
```

### WooCommerce Implementation

```php
<!-- Add to functions.php -->
<?php
function add_ecommerce_tracking_data() {
    if (is_product()) {
        global $product;
        ?>
        <script>
        window.productData = {
            id: <?php echo $product->get_id(); ?>,
            name: <?php echo json_encode($product->get_name()); ?>,
            category: <?php echo json_encode(wp_get_post_terms($product->get_id(), 'product_cat')[0]->name ?? ''); ?>,
            price: <?php echo $product->get_price(); ?>,
            currency: '<?php echo get_woocommerce_currency(); ?>',
            inStock: <?php echo $product->is_in_stock() ? 'true' : 'false'; ?>
        };
        </script>
        <?php
    }
    
    if (is_cart()) {
        global $woocommerce;
        $cart = $woocommerce->cart;
        ?>
        <script>
        window.cartData = {
            totalItems: <?php echo $cart->get_cart_contents_count(); ?>,
            totalValue: <?php echo $cart->get_cart_total(); ?>,
            currency: '<?php echo get_woocommerce_currency(); ?>'
        };
        </script>
        <?php
    }
}
add_action('wp_head', 'add_ecommerce_tracking_data');
?>
```

## Helper Functions

### Essential E-commerce Helper Functions

```html
<script>
// Helper functions for e-commerce tracking
function getCartItemCount() {
    // Implement based on your cart system
    return window.cartData ? window.cartData.totalItems : 0;
}

function getCartTotal() {
    // Implement based on your cart system
    return window.cartData ? window.cartData.totalValue : 0;
}

function getTimeOnPage() {
    return Math.round((Date.now() - window.pageStartTime) / 1000);
}

function getSessionDuration() {
    const sessionStart = sessionStorage.getItem('sessionStart') || Date.now();
    return Math.round((Date.now() - sessionStart) / 1000 / 60); // minutes
}

function getTrafficSource() {
    const referrer = document.referrer;
    if (!referrer) return 'direct';
    if (referrer.includes('google')) return 'google';
    if (referrer.includes('facebook')) return 'facebook';
    if (referrer.includes('instagram')) return 'instagram';
    return 'referral';
}

function getPagesVisited() {
    const visited = sessionStorage.getItem('pagesVisited');
    return visited ? JSON.parse(visited).length : 1;
}

function getImagesViewed() {
    // Track image carousel interactions
    return document.querySelectorAll('.product-image:viewed').length || 1;
}

function getReviewsRead() {
    // Track if user has scrolled to reviews section
    return document.querySelector('.reviews-section:in-view') ? true : false;
}

// Initialize session tracking
if (!sessionStorage.getItem('sessionStart')) {
    sessionStorage.setItem('sessionStart', Date.now());
}
window.pageStartTime = Date.now();
</script>
```

## Analytics Dashboard Setup

### Key E-commerce Metrics to Track

1. **Conversion Funnel Metrics**
   - Product Views → Add to Cart → Checkout Started → Purchase
   - Conversion rates at each step
   - Drop-off analysis

2. **Revenue Metrics**
   - Total revenue
   - Average order value (AOV)
   - Revenue per visitor (RPV)
   - Customer lifetime value (CLV)

3. **Product Performance**
   - Best-selling products
   - Product view-to-purchase rates
   - Category performance
   - Inventory turnover

4. **Customer Behavior**
   - New vs returning customer ratios
   - Shopping cart analysis
   - Payment method preferences
   - Geographic performance

### Custom Reports Configuration

Create custom reports in Sealmetrics for:
- **Sales Performance**: Track revenue by product, category, and time period
- **Conversion Analysis**: Monitor funnel performance and identify bottlenecks
- **Customer Segmentation**: Analyze behavior by customer type and value
- **Marketing Attribution**: Understand which channels drive sales

This comprehensive setup provides complete visibility into your e-commerce performance while maintaining full privacy compliance through Sealmetrics' consentless analytics platform.