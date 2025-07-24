# Industry-Specific Use Cases and Implementation

## E-commerce Use Cases

### Product Page Tracking

**Scenario:** Track product views and category performance
```html
<!-- Product page tracking -->
<script>
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

### Add to Cart Events

**Scenario:** Track when customers add products to cart
```html
<button onclick="addToCart('SKU123', 49.99)">Add to Cart</button>

<script>
function addToCart(productSku, price) {
    // Your add to cart logic here
    
    // Track the event
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Add to Cart',
       value: price,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Purchase Completion

**Scenario:** Track completed purchases and revenue
```html
<!-- Thank you page - Purchase completion -->
<script>
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'purchase',
   label: 'Order Completed',
   value: 149.99,
   currency: 'USD',
   ignore_pageview: 1,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### Abandoned Cart Recovery

**Scenario:** Track cart abandonment for recovery campaigns
```html
<script>
// Track when user leaves checkout page
window.addEventListener('beforeunload', function() {
    if (cartHasItems && !purchaseCompleted) {
        (function() {
        var options = {
           account: 'YOUR_ACCOUNT_ID_HERE',
           event: 'microconversion',
           label: 'Cart Abandoned',
           value: getCartTotal(),
           ignore_pageview: 1,
           use_session: 1,
        };
        var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
        })();
    }
});
</script>
```

---

## SaaS Use Cases

### Free Trial Signup

**Scenario:** Track free trial registrations
```html
<!-- Trial signup form -->
<form id="trial-form" onsubmit="trackTrialSignup()">
    <input type="email" name="email" required>
    <button type="submit">Start Free Trial</button>
</form>

<script>
function trackTrialSignup() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Free Trial Signup',
       value: 0,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Subscription Upgrade

**Scenario:** Track when users upgrade their plans
```html
<script>
function trackSubscriptionUpgrade(planName, monthlyValue) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'purchase',
       label: 'Subscription Upgrade: ' + planName,
       value: monthlyValue,
       currency: 'USD',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Usage
trackSubscriptionUpgrade('Pro Plan', 29.99);
</script>
```

### Feature Usage Tracking

**Scenario:** Track key feature adoption
```html
<script>
function trackFeatureUsage(featureName) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'Feature Used: ' + featureName,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Track when users use specific features
document.getElementById('export-button').addEventListener('click', function() {
    trackFeatureUsage('Data Export');
});

document.getElementById('integrate-api').addEventListener('click', function() {
    trackFeatureUsage('API Integration');
});
</script>
```

### Demo Request

**Scenario:** Track demo requests from prospects
```html
<form id="demo-form" onsubmit="trackDemoRequest()">
    <input type="text" name="company" placeholder="Company Name" required>
    <input type="email" name="email" placeholder="Email" required>
    <button type="submit">Request Demo</button>
</form>

<script>
function trackDemoRequest() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Demo Request',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Insurance Use Cases

### Quote Request Tracking

**Scenario:** Track insurance quote requests
```html
<form id="quote-form" onsubmit="trackQuoteRequest()">
    <select name="insurance-type">
        <option value="auto">Auto Insurance</option>
        <option value="home">Home Insurance</option>
        <option value="life">Life Insurance</option>
    </select>
    <input type="email" name="email" required>
    <button type="submit">Get Quote</button>
</form>

<script>
function trackQuoteRequest() {
    const insuranceType = document.querySelector('select[name="insurance-type"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Quote Request: ' + insuranceType.charAt(0).toUpperCase() + insuranceType.slice(1),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Policy Purchase

**Scenario:** Track completed policy purchases
```html
<!-- Policy confirmation page -->
<script>
(function() {
var options = {
   account: 'YOUR_ACCOUNT_ID_HERE',
   event: 'purchase',
   label: 'Policy Purchase: Auto Insurance',
   value: 890.00,
   currency: 'USD',
   ignore_pageview: 1,
   use_session: 1,
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

### Claims Form Submission

**Scenario:** Track insurance claim submissions
```html
<form id="claims-form" onsubmit="trackClaimSubmission()">
    <input type="text" name="policy-number" placeholder="Policy Number" required>
    <textarea name="claim-description" placeholder="Describe your claim" required></textarea>
    <button type="submit">Submit Claim</button>
</form>

<script>
function trackClaimSubmission() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Insurance Claim Submitted',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Healthcare Use Cases

### Appointment Booking

**Scenario:** Track medical appointment bookings
```html
<form id="appointment-form" onsubmit="trackAppointmentBooking()">
    <select name="service-type">
        <option value="consultation">General Consultation</option>
        <option value="checkup">Annual Checkup</option>
        <option value="specialist">Specialist Visit</option>
    </select>
    <input type="date" name="appointment-date" required>
    <button type="submit">Book Appointment</button>
</form>

<script>
function trackAppointmentBooking() {
    const serviceType = document.querySelector('select[name="service-type"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Appointment Booked: ' + serviceType.replace('-', ' ').replace(/\b\w/g, l => l.toUpperCase()),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Patient Portal Registration

**Scenario:** Track patient portal signups
```html
<form id="portal-registration" onsubmit="trackPortalRegistration()">
    <input type="text" name="patient-id" placeholder="Patient ID" required>
    <input type="email" name="email" placeholder="Email" required>
    <button type="submit">Create Account</button>
</form>

<script>
function trackPortalRegistration() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Patient Portal Registration',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Telehealth Session Start

**Scenario:** Track telehealth session initiations
```html
<script>
function startTelehealthSession() {
    // Your telehealth logic here
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'Telehealth Session Started',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## B2B Services Use Cases

### Contact Form Submissions

**Scenario:** Track business inquiry forms
```html
<form id="contact-form" onsubmit="trackB2BContact()">
    <input type="text" name="company" placeholder="Company Name" required>
    <input type="email" name="email" placeholder="Business Email" required>
    <select name="service-interest">
        <option value="consulting">Consulting Services</option>
        <option value="software">Software Solutions</option>
        <option value="training">Training Programs</option>
    </select>
    <button type="submit">Get In Touch</button>
</form>

<script>
function trackB2BContact() {
    const serviceInterest = document.querySelector('select[name="service-interest"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'B2B Contact: ' + serviceInterest.charAt(0).toUpperCase() + serviceInterest.slice(1),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Whitepaper Download

**Scenario:** Track valuable content downloads
```html
<button onclick="downloadWhitepaper('Digital Transformation Guide 2025')">Download Whitepaper</button>

<script>
function downloadWhitepaper(whitepaperTitle) {
    // Your download logic here (e.g., open PDF)
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'download',
       label: 'Whitepaper: ' + whitepaperTitle,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Webinar Registration

**Scenario:** Track webinar signups
```html
<form id="webinar-form" onsubmit="trackWebinarRegistration()">
    <input type="text" name="name" placeholder="Full Name" required>
    <input type="email" name="email" placeholder="Email" required>
    <input type="text" name="company" placeholder="Company" required>
    <button type="submit">Register for Webinar</button>
</form>

<script>
function trackWebinarRegistration() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Webinar Registration',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Education Use Cases

### Course Enrollment

**Scenario:** Track online course enrollments
```html
<button onclick="enrollInCourse('Advanced Marketing Strategy', 299.00)">Enroll Now</button>

<script>
function enrollInCourse(courseName, price) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'purchase',
       label: 'Course Enrollment: ' + courseName,
       value: price,
       currency: 'USD',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Admission Application

**Scenario:** Track university admission applications
```html
<form id="admission-form" onsubmit="trackAdmissionApplication()">
    <input type="text" name="student-name" placeholder="Full Name" required>
    <select name="program">
        <option value="undergraduate">Undergraduate Program</option>
        <option value="graduate">Graduate Program</option>
        <option value="doctorate">Doctorate Program</option>
    </select>
    <button type="submit">Submit Application</button>
</form>

<script>
function trackAdmissionApplication() {
    const program = document.querySelector('select[name="program"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Admission Application: ' + program.charAt(0).toUpperCase() + program.slice(1),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Resource Download

**Scenario:** Track educational resource downloads
```html
<button onclick="downloadResource('Study Guide: Statistics 101')">Download Study Guide</button>

<script>
function downloadResource(resourceName) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'download',
       label: resourceName,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Real Estate Use Cases

### Property Inquiry

**Scenario:** Track property interest inquiries
```html
<form id="property-inquiry" onsubmit="trackPropertyInquiry()">
    <input type="text" name="property-id" placeholder="Property ID" required>
    <input type="email" name="email" placeholder="Your Email" required>
    <select name="inquiry-type">
        <option value="viewing">Schedule Viewing</option>
        <option value="information">More Information</option>
        <option value="offer">Make Offer</option>
    </select>
    <button type="submit">Submit Inquiry</button>
</form>

<script>
function trackPropertyInquiry() {
    const inquiryType = document.querySelector('select[name="inquiry-type"]').value;
    const propertyId = document.querySelector('input[name="property-id"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Property Inquiry: ' + inquiryType.charAt(0).toUpperCase() + inquiryType.slice(1),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Mortgage Calculator Usage

**Scenario:** Track mortgage calculator engagement
```html
<button onclick="calculateMortgage()">Calculate Monthly Payment</button>

<script>
function calculateMortgage() {
    // Your mortgage calculation logic here
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'Mortgage Calculator Used',
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Financial Services Use Cases

### Loan Application

**Scenario:** Track loan application submissions
```html
<form id="loan-application" onsubmit="trackLoanApplication()">
    <select name="loan-type">
        <option value="personal">Personal Loan</option>
        <option value="business">Business Loan</option>
        <option value="mortgage">Mortgage</option>
    </select>
    <input type="number" name="loan-amount" placeholder="Loan Amount" required>
    <button type="submit">Apply Now</button>
</form>

<script>
function trackLoanApplication() {
    const loanType = document.querySelector('select[name="loan-type"]').value;
    const loanAmount = document.querySelector('input[name="loan-amount"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Loan Application: ' + loanType.charAt(0).toUpperCase() + loanType.slice(1),
       value: parseFloat(loanAmount),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Account Opening

**Scenario:** Track new account creations
```html
<form id="account-opening" onsubmit="trackAccountOpening()">
    <select name="account-type">
        <option value="checking">Checking Account</option>
        <option value="savings">Savings Account</option>
        <option value="investment">Investment Account</option>
    </select>
    <input type="email" name="email" placeholder="Email" required>
    <button type="submit">Open Account</button>
</form>

<script>
function trackAccountOpening() {
    const accountType = document.querySelector('select[name="account-type"]').value;
    
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Account Opening: ' + accountType.charAt(0).toUpperCase() + accountType.slice(1),
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

## Implementation Best Practices by Industry

### E-commerce Best Practices
- **Track the full funnel**: Product views → Add to cart → Checkout → Purchase
- **Use monetary values**: Always include price/value for revenue tracking
- **Category tracking**: Include product categories in labels
- **Abandoned cart**: Implement exit-intent cart abandonment tracking

### SaaS Best Practices
- **Trial to paid conversion**: Track the complete customer journey
- **Feature adoption**: Monitor which features drive retention
- **Upgrade paths**: Track progression through different plan tiers
- **Churn indicators**: Monitor usage patterns that predict churn

### Lead Generation Best Practices
- **Form progression**: Track form starts vs completions
- **Lead quality scoring**: Use different event types for different lead qualities
- **Multi-step forms**: Track each step of complex forms
- **Thank you pages**: Always track conversion completion

### Content Marketing Best Practices
- **Download attribution**: Connect downloads to traffic sources
- **Engagement depth**: Track how deep users go into content
- **Video completion**: Monitor video engagement rates
- **Newsletter signups**: Track content-to-subscriber conversion

## Testing and Optimization

### A/B Testing Integration
```html
<!-- Example: A/B test different CTA buttons -->
<script>
// Determine test variant (your A/B testing logic)
const variant = Math.random() < 0.5 ? 'A' : 'B';

function trackCTAClick() {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'CTA Click - Variant ' + variant,
       ignore_pageview: 1,
       use_session: 1,
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Performance Monitoring
- Monitor page load impact of tracking codes
- Test tracking accuracy across different browsers
- Verify events fire correctly in production
- Regular audit of tracking implementation

This comprehensive guide provides industry-specific implementations using Sealmetrics' privacy-first tracking technology, ensuring compliance while capturing essential business intelligence across diverse sectors.