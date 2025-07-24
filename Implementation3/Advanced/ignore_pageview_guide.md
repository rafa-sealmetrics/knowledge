# Understanding Ignore Page View Parameter

## What is Ignore Page View?

The `ignore_pageview` parameter is a crucial control mechanism in Sealmetrics tracking that determines whether an event should trigger an associated page view or not. This parameter gives you precise control over when pageviews are recorded, preventing duplicate tracking and ensuring clean analytics data.

## Core Concept

**Every event in Sealmetrics is fundamentally associated with a page view.** However, there are scenarios where you want to track an event (like a microconversion or custom action) without recording an additional page view. This is where `ignore_pageview` becomes essential.

## When to Use Ignore Page View

### 1. **Duplicate Page View Prevention**
When you already have automatic pageview tracking (e.g., through GTM) and don't want additional pageviews recorded with your custom events.

### 2. **Non-Page Events**
For tracking actions that don't represent actual page navigation, such as:
- Cookie banner interactions
- Modal/popup interactions  
- Video play events
- Form step completions
- Download clicks
- Button interactions

### 3. **Multiple Events on Same Page**
When tracking multiple events on a single page where only one pageview should be counted.

## Syntax and Implementation

### With Ignore Page View (ignore_pageview: 1)

**Use Case:** Track event without additional pageview
```html
<script>
/* SealMetrics Tracker Code - WITH Ignore Page View */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'microconversion',
   label: 'Paso1-Funnel',
   ignore_pageview: 1,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Tracker Code */
</script>
```

### Without Ignore Page View (Default Behavior)

**Use Case:** Track event AND record pageview
```html
<script>
/* SealMetrics Tracker Code - WITHOUT Ignore Page View */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'microconversion',
   label: 'Paso1-Funnel',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Tracker Code */
</script>
```

## Practical Implementation Examples

### Example 1: Cookie Banner Tracking

**Scenario:** Track cookie banner interactions without counting them as page views

```html
<!-- Cookie Banner HTML -->
<div id="cookie-banner">
    <p>We use cookies to improve your experience.</p>
    <button onclick="acceptCookies()">Accept</button>
    <button onclick="rejectCookies()">Reject</button>
</div>

<script>
function acceptCookies() {
    // Hide banner logic here
    
    // Track event WITHOUT page view
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Cookie Banner Accept',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

function rejectCookies() {
    // Hide banner logic here
    
    // Track event WITHOUT page view
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Cookie Banner Reject',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Example 2: Multi-Step Form Tracking

**Scenario:** Track form progression without multiple page views

```html
<!-- Multi-step form -->
<form id="registration-form">
    <div id="step1" class="form-step">
        <input type="email" name="email" placeholder="Email" required>
        <button type="button" onclick="nextStep(2)">Continue</button>
    </div>
    
    <div id="step2" class="form-step" style="display:none;">
        <input type="text" name="company" placeholder="Company" required>
        <button type="button" onclick="nextStep(3)">Continue</button>
    </div>
    
    <div id="step3" class="form-step" style="display:none;">
        <input type="tel" name="phone" placeholder="Phone" required>
        <button type="submit">Complete Registration</button>
    </div>
</form>

<script>
function nextStep(stepNumber) {
    // Show next step logic here
    
    // Track step progression WITHOUT page view
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Form Step ' + stepNumber + ' Reached',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Example 3: Video Engagement Tracking

**Scenario:** Track video interactions without page view inflation

```html
<!-- Video player -->
<video id="product-demo" controls>
    <source src="product-demo.mp4" type="video/mp4">
</video>

<script>
const video = document.getElementById('product-demo');

// Track video play WITHOUT page view
video.addEventListener('play', function() {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Video Play Started',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
});

// Track video completion WITHOUT page view
video.addEventListener('ended', function() {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Video Completed',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
});
</script>
```

### Example 4: Download Tracking

**Scenario:** Track file downloads without additional page views

```html
<!-- Download buttons -->
<button onclick="downloadFile('Product Brochure PDF')">Download Brochure</button>
<button onclick="downloadFile('Technical Specification')">Download Specs</button>

<script>
function downloadFile(fileName) {
    // Your download logic here
    
    // Track download WITHOUT page view
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'download',
       label: fileName + ' Downloaded',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## Google Tag Manager Integration

### GTM Setup with Ignore Page View

**Scenario:** You have GTM handling pageviews automatically, but want to track custom events

```html
<!-- GTM Custom HTML Tag for Events -->
<script>
(function() {
var options = {
   account: '000000000000000000001234',
   event: '{{Event Category}}',
   label: '{{Event Label}}',
   ignore_pageview: 1,  // Prevent duplicate page views
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

## Decision Matrix: When to Use Ignore Page View

| Scenario | Use ignore_pageview: 1 | Use Default Behavior |
|----------|----------------------|---------------------|
| **Automatic GTM pageview tracking exists** | ✅ Yes | ❌ No |
| **Multiple events on same page** | ✅ Yes | ❌ No |
| **Button/link clicks** | ✅ Yes | ❌ No |
| **Form interactions** | ✅ Yes | ❌ No |
| **Modal/popup interactions** | ✅ Yes | ❌ No |
| **Video/audio controls** | ✅ Yes | ❌ No |
| **Cookie banner interactions** | ✅ Yes | ❌ No |
| **AJAX form submissions** | ✅ Yes | ❌ No |
| **Page navigation events** | ❌ No | ✅ Yes |
| **Thank you page tracking** | ❌ No | ✅ Yes |
| **Single event per page load** | ❌ No | ✅ Yes |

## Common Use Cases by Industry

### E-commerce
```html
<!-- Add to Cart Button (ignore pageview) -->
<button onclick="addToCart()">Add to Cart</button>

<script>
function addToCart() {
    // Add to cart logic here
    
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Add to Cart',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### SaaS Applications
```html
<!-- Feature Usage Tracking (ignore pageview) -->
<button onclick="useFeature('Data Export')">Export Data</button>

<script>
function useFeature(featureName) {
    // Feature logic here
    
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'custom',
       label: 'Feature Used: ' + featureName,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Lead Generation
```html
<!-- Progressive Form Steps (ignore pageview) -->
<script>
function trackFormProgress(stepName) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Form Progress: ' + stepName,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Usage
trackFormProgress('Email Entered');
trackFormProgress('Company Info Added');
trackFormProgress('Phone Number Added');
</script>
```

## Advanced Implementation Patterns

### Conditional Ignore Page View

```html
<script>
function trackEventConditionally(eventLabel, shouldIgnorePageview) {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: eventLabel,
       use_session: 1,
    };
    
    // Only add ignore_pageview if needed
    if (shouldIgnorePageview) {
        options.ignore_pageview = 1;
    }
    
    (function() {
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Usage examples
trackEventConditionally('Button Click', true);  // Ignores pageview
trackEventConditionally('Page Navigation', false); // Includes pageview
</script>
```

### Smart Page View Detection

```html
<script>
// Automatically determine if pageview should be ignored
function smartTrackEvent(eventType, eventLabel) {
    var hasExistingPageviewTracking = typeof gtag !== 'undefined' || 
                                     typeof ga !== 'undefined' || 
                                     window.dataLayer || 
                                     document.querySelector('[data-gtm-id]');
    
    var options = {
       account: '000000000000000000001234',
       event: eventType,
       label: eventLabel,
       use_session: 1,
    };
    
    // If other tracking exists, ignore pageview to prevent duplicates
    if (hasExistingPageviewTracking) {
        options.ignore_pageview = 1;
    }
    
    (function() {
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## Debugging and Testing

### Console Logging for Testing

```html
<script>
function trackWithDebug(eventLabel, ignorePageview) {
    console.log('Tracking event:', eventLabel, 'Ignore pageview:', ignorePageview);
    
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: eventLabel,
       use_session: 1,
    };
    
    if (ignorePageview) {
        options.ignore_pageview = 1;
        console.log('Pageview will be ignored for this event');
    } else {
        console.log('Pageview will be recorded with this event');
    }
    
    (function() {
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Testing Checklist

- [ ] **Verify Event Firing**: Check browser network tab for tracking calls
- [ ] **Page View Count**: Ensure pageviews aren't inflated when using ignore_pageview: 1
- [ ] **Event Attribution**: Confirm events are properly attributed to sessions
- [ ] **Multiple Events**: Test multiple events on same page with ignore_pageview
- [ ] **GTM Integration**: Verify no conflicts with existing GTM pageview tracking
- [ ] **Cross-Browser Testing**: Test ignore_pageview behavior across browsers

## Best Practices

### 1. **Consistent Usage**
Always use `ignore_pageview: 1` for interaction events that don't represent page navigation.

### 2. **Documentation**
Document which events use ignore_pageview and why, for team clarity.

### 3. **GTM Strategy**
If using GTM for pageviews, consistently use `ignore_pageview: 1` for all custom events.

### 4. **Event Naming**
Use clear event labels that indicate the nature of the interaction.

### 5. **Testing Protocol**
Always test pageview counts before and after implementing ignore_pageview.

## Common Mistakes to Avoid

### ❌ **Mistake 1: Ignoring Pageviews for Navigation Events**
```html
<!-- WRONG: This should record a pageview -->
<script>
var options = {
   account: '000000000000000000001234',
   event: 'pageview',
   ignore_pageview: 1,  // This defeats the purpose
   use_session: 1,
};
</script>
```

### ❌ **Mistake 2: Not Ignoring Pageviews with GTM**
```html
<!-- WRONG: This will double-count pageviews if GTM is active -->
<script>
var options = {
   account: '000000000000000000001234',
   event: 'microconversion',
   label: 'Button Click',
   // Missing ignore_pageview: 1
   use_session: 1,
};
</script>
```

### ❌ **Mistake 3: Inconsistent Usage**
Using ignore_pageview randomly without a clear strategy leads to unreliable data.

## Summary

The `ignore_pageview` parameter is essential for:

- **Clean Data**: Preventing pageview inflation from interaction events
- **GTM Compatibility**: Avoiding conflicts with existing tracking systems  
- **Accurate Analytics**: Ensuring events and pageviews are properly attributed
- **Flexible Implementation**: Giving precise control over tracking behavior

**Key Rule:** Use `ignore_pageview: 1` for any event that represents an interaction within a page rather than navigation to a page.

By properly implementing the ignore_pageview parameter, you ensure accurate, clean analytics data that truly reflects user behavior and page performance on your website.