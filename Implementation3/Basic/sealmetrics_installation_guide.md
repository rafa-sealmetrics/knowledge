# Sealmetrics Installation Guide

## Quick Start Installation

### Step 1: Get Your Account ID

Before installation, you'll need your unique Sealmetrics Account ID. This is a 24-character identifier that looks like: `000000000000000000001234`

You can find your Account ID in your Sealmetrics dashboard under **Settings > Installation**.

### Step 2: Basic Pageview Tracking

Copy and paste this code into the `<head>` section of every page you want to track:

```html
<script>
/* SealMetrics Tracker Code */
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'pageview',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Tracker Code */
</script>
```

**Important:** Replace `YOUR_ACCOUNT_ID_HERE` with your actual Account ID.

### Step 3: Verify Installation

1. Install the code on your website
2. Visit a page with the tracking code
3. Check your Sealmetrics dashboard for real-time data (may take a few minutes)
4. Look for the page view in your analytics

## Advanced Installation Options

### Custom Event Tracking

For tracking specific actions like form submissions, downloads, or button clicks:

```html
<script>
/* SealMetrics Event Tracker Code */
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'microconversion',
   label: 'Contact Form Submission',
   ignore_pageview: 1,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Event Tracker Code */
</script>
```

### E-commerce Purchase Tracking

For tracking sales and revenue:

```html
<script>
/* SealMetrics Purchase Tracker Code */
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'purchase',
   label: 'Online Purchase',
   value: 99.99,
   currency: 'USD',
   ignore_pageview: 1,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
/* End SealMetrics Purchase Tracker Code */
</script>
```

## Installation Methods

### Method 1: HTML Integration (Recommended)

**For Static Websites:**
1. Add the basic pageview code to your HTML template's `<head>` section
2. Add event tracking codes where specific actions occur
3. Replace Account ID in all instances

**For WordPress:**
1. Go to **Appearance > Theme Editor**
2. Edit `header.php`
3. Add the code before the closing `</head>` tag
4. Save changes

**For Shopify:**
1. Go to **Online Store > Themes**
2. Click **Actions > Edit Code**
3. Edit `theme.liquid`
4. Add the code before `</head>`
5. Save changes

### Method 2: Google Tag Manager

**Setup Steps:**
1. Create a new Custom HTML tag in GTM
2. Paste the Sealmetrics tracking code
3. Set trigger to "All Pages" for pageview tracking
4. Create additional tags for custom events
5. Publish the container

**GTM Custom HTML Tag:**
```html
<script>
/* SealMetrics GTM Integration */
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'pageview',
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### Method 3: WordPress Plugin

1. Install the official Sealmetrics WordPress plugin
2. Go to **Settings > Sealmetrics**
3. Enter your Account ID
4. Configure tracking options
5. Save settings

## Configuration Parameters

### Required Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `account` | Your Sealmetrics Account ID | `'000000000000000000001234'` |
| `event` | Type of event to track | `'pageview'`, `'microconversion'`, `'purchase'` |

### Optional Parameters

| Parameter | Description | Example | Default |
|-----------|-------------|---------|---------|
| `use_session` | Enable session tracking | `1` or `0` | `1` |
| `label` | Custom event label | `'Contact Form'` | `null` |
| `value` | Monetary value | `99.99` | `null` |
| `currency` | Currency code | `'USD'`, `'EUR'` | `'USD'` |
| `ignore_pageview` | Skip automatic pageview | `1` or `0` | `0` |

### Event Types

| Event Type | Purpose | When to Use |
|------------|---------|-------------|
| `pageview` | Page view tracking | Automatic page tracking |
| `microconversion` | Lead generation events | Form submissions, signups |
| `purchase` | E-commerce transactions | Completed purchases |
| `download` | File downloads | PDF, software downloads |
| `video_play` | Video engagement | Video play events |
| `custom` | Custom business events | Any business-specific action |

## Implementation Examples

### Form Submission Tracking

```html
<!-- Contact Form -->
<form id="contact-form" onsubmit="trackFormSubmission()">
    <!-- form fields -->
    <button type="submit">Submit</button>
</form>

<script>
function trackFormSubmission() {
    // Sealmetrics event tracking
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Contact Form Submission',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Button Click Tracking

```html
<button onclick="trackButtonClick('Download Brochure')">Download Brochure</button>

<script>
function trackButtonClick(buttonLabel) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'download',
       label: buttonLabel,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Dynamic Event Tracking

```javascript
// Function to track any custom event
function trackSealmetricsEvent(eventType, eventLabel, eventValue) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: eventType,
       label: eventLabel,
       ignore_pageview: 1,
       use_session: 1,
    };
    
    if (eventValue) {
        options.value = eventValue;
    }
    
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Usage examples:
// trackSealmetricsEvent('microconversion', 'Newsletter Signup');
// trackSealmetricsEvent('purchase', 'Product Purchase', 149.99);
// trackSealmetricsEvent('custom', 'Video Watched');
```

## Single Page Applications (SPA)

### React Implementation

```jsx
// React hook for Sealmetrics tracking
import { useEffect } from 'react';

const useSealmetrics = (accountId) => {
  const trackPageview = () => {
    (function() {
    var options = {
       account: accountId,
       event: 'pageview',
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
  };

  const trackEvent = (eventType, label, value) => {
    (function() {
    var options = {
       account: accountId,
       event: eventType,
       label: label,
       ignore_pageview: 1,
       use_session: 1,
    };
    if (value) options.value = value;
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
  };

  return { trackPageview, trackEvent };
};

// Component usage
const MyComponent = () => {
  const { trackPageview, trackEvent } = useSealmetrics('YOUR_ACCOUNT_ID_HERE');

  useEffect(() => {
    trackPageview();
  }, []);

  const handleFormSubmit = () => {
    trackEvent('microconversion', 'Contact Form');
  };

  return (
    <form onSubmit={handleFormSubmit}>
      {/* form content */}
    </form>
  );
};
```

### Vue.js Implementation

```javascript
// Vue.js mixin for Sealmetrics
const SealmetricsMixin = {
  methods: {
    trackSealmetricsPageview() {
      (function() {
      var options = {
         account: 'YOUR_ACCOUNT_ID_HERE',
         event: 'pageview',
         use_session: 1,
      };
      var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
      })();
    },
    
    trackSealmetricsEvent(eventType, label, value) {
      (function() {
      var options = {
         account: 'YOUR_ACCOUNT_ID_HERE',
         event: eventType,
         label: label,
         ignore_pageview: 1,
         use_session: 1,
      };
      if (value) options.value = value;
      var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
      })();
    }
  }
}
```

## Testing and Validation

### Browser Console Testing

1. Open browser developer tools (F12)
2. Go to the Console tab
3. Visit a page with Sealmetrics installed
4. Look for successful loading messages
5. Check for any error messages

### Real-Time Dashboard Verification

1. Install tracking code on a test page
2. Visit the page from different devices/browsers
3. Check Sealmetrics dashboard for real-time data
4. Verify events are being recorded correctly

### Debug Mode

Add `debug: 1` to your options for detailed console logging:

```javascript
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'pageview',
   use_session: 1,
   debug: 1,  // Enable debug mode
};
```

## Troubleshooting

### Common Issues

**1. No Data Appearing**
- Verify Account ID is correct
- Check for JavaScript errors in browser console
- Ensure code is in the `<head>` section
- Wait up to 10 minutes for data to appear

**2. Events Not Tracking**
- Confirm `ignore_pageview: 1` is set for custom events
- Check event is triggered properly (use console.log)
- Verify event name is correct

**3. Multiple Pageviews**
- Ensure only one pageview tracker per page
- Check for duplicate installations
- Use `ignore_pageview: 1` for event-only tracking

**4. SPA Not Tracking Route Changes**
- Manually call tracking on route changes
- Use framework-specific implementations above
- Ensure pageview tracking on each route

### Performance Optimization

**Best Practices:**
- Place pageview tracking in `<head>`
- Use async loading (built into Sealmetrics code)
- Minimize number of custom events per page
- Test performance impact with browser dev tools

### Security Considerations

- Sealmetrics tracking is privacy-first by design
- No personal data is collected
- No cookies are used
- GDPR compliant without consent requirements

## Getting Help

**Support Resources:**
- Documentation: help.sealmetrics.com
- Email Support: support@sealmetrics.com
- Community Forum: Available in dashboard
- Live Chat: Available during business hours

**Before Contacting Support:**
- Have your Account ID ready
- Include relevant code snippets
- Describe expected vs actual behavior
- Include browser console errors if any