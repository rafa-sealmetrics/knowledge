# Content Grouping Implementation Guide

## What is Content Grouping?

Content Grouping is a powerful analytics feature that allows you to categorize and organize your website content for better insights and reporting. Instead of analyzing individual page performance, Content Grouping enables you to group related content by theme, category, section, or any custom classification that aligns with your business objectives.

## Key Benefits

- **Strategic Content Analysis**: Analyze performance by content categories rather than individual URLs
- **Improved Reporting**: Group related pages for cleaner, more meaningful analytics reports  
- **User Journey Insights**: Track engagement patterns across content themes and categories
- **Business-Aligned Analytics**: Organize data according to your business structure and goals

## Basic Implementation

### Standard Content Grouping Pixel

```html
<script>
/* SealMetrics Tracker Code with Content Grouping */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'custom-name',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Tracker Code */
</script>
```

## Content Grouping Strategies

### 1. Blog Content Organization

**Marketing Blog Posts:**
```html
<script>
/* Marketing Blog Content Group */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'blog-marketing',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

**Technology Blog Posts:**
```html
<script>
/* Technology Blog Content Group */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'blog-technology',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### 2. E-commerce Product Categories

**Electronics Products:**
```html
<script>
/* Electronics Product Pages */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'products-electronics',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

**Fashion & Clothing:**
```html
<script>
/* Fashion & Clothing Product Pages */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'products-fashion',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### 3. Website Section Grouping

**Support & Help Center:**
```html
<script>
/* Support Center Pages */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'support-center',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

**Company Information:**
```html
<script>
/* Company Information Pages */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: 'company-info',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

## Dynamic Content Grouping

### JavaScript-Based Dynamic Grouping

```html
<script>
/* Dynamic Content Grouping Based on URL */
function getContentGroup() {
    const path = window.location.pathname;
    const hostname = window.location.hostname;
    
    // Blog categorization
    if (path.includes('/blog/')) {
        if (path.includes('/marketing/')) return 'blog-marketing';
        if (path.includes('/technology/')) return 'blog-technology';
        if (path.includes('/business/')) return 'blog-business';
        return 'blog-general';
    }
    
    // Product categorization
    if (path.includes('/products/')) {
        if (path.includes('/electronics/')) return 'products-electronics';
        if (path.includes('/fashion/')) return 'products-fashion';
        if (path.includes('/home/')) return 'products-home';
        return 'products-general';
    }
    
    // Support section
    if (path.includes('/support/') || path.includes('/help/')) {
        if (path.includes('/tutorials/')) return 'support-tutorials';
        if (path.includes('/faq/')) return 'support-faq';
        return 'support-general';
    }
    
    // Company pages
    if (path.includes('/about/') || path.includes('/company/')) {
        return 'company-info';
    }
    
    // Landing pages
    if (path.includes('/landing/') || path.includes('/lp/')) {
        return 'landing-pages';
    }
    
    // Homepage
    if (path === '/' || path === '/index.html') {
        return 'homepage';
    }
    
    return 'general-content';
}

/* Dynamic Content Grouping Implementation */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: getContentGroup(),
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

## Advanced Content Grouping Strategies

### 1. User Journey-Based Grouping

```html
<script>
/* User Journey Stage Grouping */
function getJourneyStage() {
    const path = window.location.pathname;
    
    // Awareness stage content
    if (path.includes('/blog/') || path.includes('/guides/') || path.includes('/resources/')) {
        return 'journey-awareness';
    }
    
    // Consideration stage content
    if (path.includes('/products/') || path.includes('/services/') || path.includes('/features/')) {
        return 'journey-consideration';
    }
    
    // Decision stage content
    if (path.includes('/pricing/') || path.includes('/demo/') || path.includes('/trial/')) {
        return 'journey-decision';
    }
    
    // Support/retention content
    if (path.includes('/support/') || path.includes('/account/') || path.includes('/dashboard/')) {
        return 'journey-retention';
    }
    
    return 'journey-general';
}
</script>
```

### 2. Audience-Based Grouping

```html
<script>
/* Audience Segment Grouping */
function getAudienceSegment() {
    const path = window.location.pathname;
    
    // Beginner-focused content
    if (path.includes('/beginner/') || path.includes('/getting-started/') || path.includes('/basics/')) {
        return 'audience-beginners';
    }
    
    // Advanced user content
    if (path.includes('/advanced/') || path.includes('/expert/') || path.includes('/pro/')) {
        return 'audience-advanced';
    }
    
    // Enterprise-focused content
    if (path.includes('/enterprise/') || path.includes('/business/') || path.includes('/corporate/')) {
        return 'audience-enterprise';
    }
    
    return 'audience-general';
}
</script>
```

## Content Grouping Best Practices

### Naming Conventions

| Good Practice | Example | Why It Works |
|---------------|---------|--------------|
| **Descriptive Names** | `blog-marketing-seo` | Clear purpose and category |
| **Consistent Format** | `products-electronics-phones` | Easy to organize and filter |
| **Hierarchical Structure** | `support-tutorials-beginner` | Enables detailed analysis |
| **Business-Aligned** | `funnel-awareness` | Matches business objectives |

### Common Content Grouping Patterns

**1. Content Type + Category:**
- `blog-marketing`
- `blog-technology` 
- `video-tutorials`
- `case-studies`

**2. Business Function + Detail:**
- `sales-landing-pages`
- `support-documentation`
- `product-comparisons`
- `pricing-calculators`

**3. User Intent + Stage:**
- `awareness-educational`
- `consideration-product-info`
- `decision-pricing`
- `retention-support`

## WordPress Integration

### Automatic Content Grouping in WordPress

```php
<!-- Add to your theme's header.php or functions.php -->
<script>
(function() {
var contentGroup = 'general-content';

<?php
// WordPress automatic content grouping
if (is_home() || is_front_page()) {
    echo 'contentGroup = "homepage";';
} elseif (is_single()) {
    // Blog posts by category
    $categories = get_the_category();
    if (!empty($categories)) {
        echo 'contentGroup = "blog-' . esc_js($categories[0]->slug) . '";';
    } else {
        echo 'contentGroup = "blog-uncategorized";';
    }
} elseif (is_page()) {
    // Pages by template or slug
    $template = get_page_template_slug();
    if ($template) {
        $template_name = basename($template, '.php');
        echo 'contentGroup = "page-' . esc_js($template_name) . '";';
    } else {
        echo 'contentGroup = "page-' . esc_js(get_post_field('post_name')) . '";';
    }
} elseif (function_exists('is_product') && is_product()) {
    // WooCommerce products by category
    $product_cats = wp_get_post_terms(get_the_ID(), 'product_cat');
    if (!empty($product_cats)) {
        echo 'contentGroup = "products-' . esc_js($product_cats[0]->slug) . '";';
    } else {
        echo 'contentGroup = "products-uncategorized";';
    }
} elseif (function_exists('is_shop') && is_shop()) {
    echo 'contentGroup = "products-shop";';
} elseif (is_search()) {
    echo 'contentGroup = "search-results";';
} elseif (is_404()) {
    echo 'contentGroup = "error-404";';
}
?>

var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   content_grouping: contentGroup,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

## Analytics Benefits

### Content Performance Analysis
- **Category Comparison**: Compare engagement across different content categories
- **Content ROI**: Measure which content types drive the most conversions
- **Resource Allocation**: Understand where to invest content creation efforts

### User Behavior Insights
- **Content Preferences**: See which content categories users engage with most
- **Navigation Patterns**: Understand how users move between content groups
- **Conversion Paths**: Track which content groups contribute to conversions

### Strategic Decision Making
- **Content Strategy**: Data-driven decisions about content development
- **Site Structure**: Optimize navigation based on content group performance
- **Marketing Focus**: Identify high-performing content themes for marketing

## Implementation Checklist

- [ ] Define content grouping strategy aligned with business goals
- [ ] Establish consistent naming conventions
- [ ] Implement basic content grouping on key page types
- [ ] Set up dynamic grouping for scalable implementation
- [ ] Test content group tracking in analytics dashboard
- [ ] Train team on content grouping best practices
- [ ] Create documentation for ongoing maintenance
- [ ] Regular review and optimization of content groups

Content Grouping transforms your analytics from page-level data into strategic business intelligence, enabling better content decisions and improved user experience optimization.