# Event Properties: Advanced Event Tracking

## What are Event Properties?

Event Properties are custom attributes that you can attach to your Sealmetrics events to capture additional context and detailed information about user interactions. While the basic event tracks *what* happened, properties tell you *how*, *where*, and *under what conditions* it happened.

Properties transform simple event tracking into rich, detailed analytics that provide deeper business insights and enable more sophisticated analysis of user behavior.

## Basic Property Implementation

### Standard Event Structure with Properties

```html
<script>
/* SealMetrics Event with Properties */
(function() {
var options = {
   account: '000000000000000000001234',
   event: 'microconversion',
   label: 'Product Purchase',
   ignore_pageview: 1,
   use_session: 1,
   // Custom Properties
   properties: {
       product_name: 'Wireless Headphones',
       category: 'Electronics',
       price: 99.99,
       currency: 'USD',
       brand: 'TechBrand',
       color: 'Black',
       size: 'Medium'
   }
};
var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
})();
</script>
```

## Industry-Specific Property Examples

### E-commerce Properties

#### Product Purchase Event
```html
<script>
function trackPurchase(productData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'purchase',
       label: 'Product Purchase',
       value: productData.price,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Product Details
           product_id: productData.sku,
           product_name: productData.name,
           category: productData.category,
           subcategory: productData.subcategory,
           brand: productData.brand,
           
           // Product Attributes
           color: productData.color,
           size: productData.size,
           material: productData.material,
           style: productData.style,
           
           // Pricing
           price: productData.price,
           discount_applied: productData.discount,
           discount_percentage: productData.discountPercent,
           final_price: productData.finalPrice,
           currency: 'USD',
           
           // Purchase Context
           payment_method: productData.paymentMethod,
           shipping_method: productData.shippingMethod,
           quantity: productData.quantity,
           
           // Customer Segment
           customer_type: productData.customerType, // 'new', 'returning', 'vip'
           membership_level: productData.membershipLevel
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Example usage
trackPurchase({
    sku: 'WH-001-BLK-M',
    name: 'Wireless Bluetooth Headphones',
    category: 'Electronics',
    subcategory: 'Audio',
    brand: 'SoundTech',
    color: 'Black',
    size: 'Medium',
    material: 'Plastic',
    style: 'Over-ear',
    price: 129.99,
    discount: 30.00,
    discountPercent: 23,
    finalPrice: 99.99,
    paymentMethod: 'Credit Card',
    shippingMethod: 'Express',
    quantity: 1,
    customerType: 'returning',
    membershipLevel: 'gold'
});
</script>
```

#### Add to Cart Event
```html
<script>
function trackAddToCart(product) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Add to Cart',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           product_id: product.id,
           product_name: product.name,
           category: product.category,
           price: product.price,
           color: product.selectedColor,
           size: product.selectedSize,
           quantity: product.quantity,
           stock_level: product.stockLevel,
           cart_total_items: getCartItemCount(),
           cart_total_value: getCartTotal(),
           product_position: product.listPosition, // Position in product list
           list_name: product.listName // 'search_results', 'category_page', 'recommendations'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### Insurance Properties

#### Quote Request Event
```html
<script>
function trackInsuranceQuote(quoteData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Insurance Quote Request',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Insurance Type
           insurance_type: quoteData.type, // 'auto', 'home', 'life', 'health'
           coverage_level: quoteData.coverageLevel, // 'basic', 'standard', 'premium'
           
           // Auto Insurance Specific
           vehicle_make: quoteData.vehicleMake,
           vehicle_model: quoteData.vehicleModel,
           vehicle_year: quoteData.vehicleYear,
           vehicle_type: quoteData.vehicleType, // 'sedan', 'suv', 'truck', 'motorcycle'
           engine_size: quoteData.engineSize,
           fuel_type: quoteData.fuelType, // 'gasoline', 'diesel', 'hybrid', 'electric'
           
           // Driver Information
           driver_age: quoteData.driverAge,
           driver_experience: quoteData.drivingExperience,
           previous_claims: quoteData.previousClaims,
           no_claims_discount: quoteData.noClaimsYears,
           
           // Location
           postal_code: quoteData.postalCode,
           parking_type: quoteData.parkingType, // 'garage', 'driveway', 'street'
           
           // Quote Details
           estimated_premium: quoteData.estimatedPremium,
           deductible: quoteData.deductible,
           policy_duration: quoteData.policyDuration, // '6_months', '12_months'
           
           // Lead Quality Indicators
           lead_source: quoteData.leadSource,
           referrer: quoteData.referrer,
           campaign: quoteData.campaign
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Example usage
trackInsuranceQuote({
    type: 'auto',
    coverageLevel: 'standard',
    vehicleMake: 'Toyota',
    vehicleModel: 'Camry',
    vehicleYear: 2020,
    vehicleType: 'sedan',
    engineSize: '2.5L',
    fuelType: 'gasoline',
    driverAge: 35,
    drivingExperience: 15,
    previousClaims: 0,
    noClaimsYears: 5,
    postalCode: '12345',
    parkingType: 'garage',
    estimatedPremium: 1200,
    deductible: 500,
    policyDuration: '12_months',
    leadSource: 'google_ads',
    referrer: 'search',
    campaign: 'auto_insurance_2024'
});
</script>
```

#### Policy Purchase Event
```html
<script>
function trackPolicyPurchase(policyData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'purchase',
       label: 'Insurance Policy Purchase',
       value: policyData.annualPremium,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           policy_number: policyData.policyNumber,
           insurance_type: policyData.type,
           coverage_amount: policyData.coverageAmount,
           annual_premium: policyData.annualPremium,
           payment_frequency: policyData.paymentFrequency, // 'monthly', 'quarterly', 'annual'
           policy_start_date: policyData.startDate,
           policy_end_date: policyData.endDate,
           
           // Customer Information
           customer_age: policyData.customerAge,
           customer_segment: policyData.customerSegment,
           
           // Sales Process
           quote_to_purchase_days: policyData.quoteToPurchaseDays,
           agent_involved: policyData.agentInvolved,
           sales_channel: policyData.salesChannel, // 'online', 'phone', 'agent', 'broker'
           
           // Policy Details (Auto Insurance)
           vehicle_value: policyData.vehicleValue,
           comprehensive_coverage: policyData.comprehensiveCoverage,
           collision_coverage: policyData.collisionCoverage
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### SaaS Properties

#### Subscription Signup Event
```html
<script>
function trackSaaSSignup(subscriptionData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'purchase',
       label: 'SaaS Subscription',
       value: subscriptionData.monthlyValue,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Subscription Details
           plan_name: subscriptionData.planName,
           plan_type: subscriptionData.planType, // 'basic', 'pro', 'enterprise'
           billing_cycle: subscriptionData.billingCycle, // 'monthly', 'annual'
           monthly_value: subscriptionData.monthlyValue,
           annual_value: subscriptionData.annualValue,
           
           // Feature Access
           user_seats: subscriptionData.userSeats,
           storage_limit: subscriptionData.storageLimit,
           api_calls_limit: subscriptionData.apiCallsLimit,
           integrations_included: subscriptionData.integrationsIncluded,
           
           // Trial Information
           had_trial: subscriptionData.hadTrial,
           trial_duration: subscriptionData.trialDuration,
           trial_to_paid_days: subscriptionData.trialToPaidDays,
           
           // Company Information
           company_size: subscriptionData.companySize,
           industry: subscriptionData.industry,
           use_case: subscriptionData.useCase,
           
           // Conversion Context
           signup_source: subscriptionData.signupSource,
           referral_code: subscriptionData.referralCode,
           discount_applied: subscriptionData.discountApplied,
           payment_method: subscriptionData.paymentMethod
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

#### Feature Usage Event
```html
<script>
function trackFeatureUsage(featureData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'custom',
       label: 'Feature Usage',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           feature_name: featureData.featureName,
           feature_category: featureData.featureCategory,
           usage_frequency: featureData.usageFrequency, // 'first_time', 'daily', 'weekly', 'power_user'
           
           // User Context
           user_plan: featureData.userPlan,
           days_since_signup: featureData.daysSinceSignup,
           user_role: featureData.userRole, // 'admin', 'user', 'viewer'
           
           // Feature Specific
           data_processed: featureData.dataProcessed,
           processing_time: featureData.processingTime,
           result_type: featureData.resultType,
           
           // Engagement
           session_duration: featureData.sessionDuration,
           actions_performed: featureData.actionsPerformed,
           help_accessed: featureData.helpAccessed
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### Real Estate Properties

#### Property Inquiry Event
```html
<script>
function trackPropertyInquiry(propertyData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Property Inquiry',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Property Details
           property_id: propertyData.propertyId,
           property_type: propertyData.propertyType, // 'house', 'apartment', 'condo', 'townhouse'
           listing_price: propertyData.listingPrice,
           square_footage: propertyData.squareFootage,
           bedrooms: propertyData.bedrooms,
           bathrooms: propertyData.bathrooms,
           
           // Location
           neighborhood: propertyData.neighborhood,
           city: propertyData.city,
           state: propertyData.state,
           zip_code: propertyData.zipCode,
           school_district: propertyData.schoolDistrict,
           
           // Property Features
           parking_spaces: propertyData.parkingSpaces,
           has_garage: propertyData.hasGarage,
           has_pool: propertyData.hasPool,
           has_garden: propertyData.hasGarden,
           year_built: propertyData.yearBuilt,
           
           // Inquiry Context
           inquiry_type: propertyData.inquiryType, // 'viewing', 'information', 'offer'
           preferred_contact: propertyData.preferredContact, // 'phone', 'email', 'text'
           viewing_preference: propertyData.viewingPreference,
           
           // Lead Information
           buyer_type: propertyData.buyerType, // 'first_time', 'investor', 'relocating'
           financing_needed: propertyData.financingNeeded,
           timeline: propertyData.timeline // 'immediate', '3_months', '6_months', 'flexible'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### Healthcare Properties

#### Appointment Booking Event
```html
<script>
function trackAppointmentBooking(appointmentData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Appointment Booked',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Appointment Details
           appointment_type: appointmentData.appointmentType, // 'consultation', 'checkup', 'specialist', 'emergency'
           service_category: appointmentData.serviceCategory, // 'general', 'cardiology', 'dermatology', 'pediatrics'
           appointment_date: appointmentData.appointmentDate,
           appointment_time: appointmentData.appointmentTime,
           duration_minutes: appointmentData.durationMinutes,
           
           // Provider Information
           doctor_name: appointmentData.doctorName,
           doctor_specialty: appointmentData.doctorSpecialty,
           clinic_location: appointmentData.clinicLocation,
           
           // Patient Context
           patient_type: appointmentData.patientType, // 'new', 'returning', 'referred'
           insurance_provider: appointmentData.insuranceProvider,
           insurance_accepted: appointmentData.insuranceAccepted,
           
           // Booking Context
           booking_channel: appointmentData.bookingChannel, // 'online', 'phone', 'walk_in'
           days_in_advance: appointmentData.daysInAdvance,
           preferred_language: appointmentData.preferredLanguage,
           
           // Urgency & Priority
           urgency_level: appointmentData.urgencyLevel, // 'routine', 'urgent', 'emergency'
           referral_source: appointmentData.referralSource,
           reason_for_visit: appointmentData.reasonForVisit
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### Financial Services Properties

#### Loan Application Event
```html
<script>
function trackLoanApplication(loanData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'microconversion',
       label: 'Loan Application',
       value: loanData.loanAmount,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Loan Details
           loan_type: loanData.loanType, // 'personal', 'mortgage', 'auto', 'business'
           loan_amount: loanData.loanAmount,
           loan_term_months: loanData.loanTermMonths,
           interest_rate: loanData.estimatedRate,
           monthly_payment: loanData.estimatedMonthlyPayment,
           
           // Applicant Information
           applicant_age: loanData.applicantAge,
           employment_status: loanData.employmentStatus, // 'employed', 'self_employed', 'retired'
           annual_income: loanData.annualIncome,
           credit_score_range: loanData.creditScoreRange, // 'excellent', 'good', 'fair', 'poor'
           debt_to_income_ratio: loanData.debtToIncomeRatio,
           
           // Mortgage Specific
           property_value: loanData.propertyValue,
           down_payment_amount: loanData.downPaymentAmount,
           down_payment_percentage: loanData.downPaymentPercentage,
           property_type: loanData.propertyType, // 'primary_residence', 'investment', 'vacation'
           
           // Auto Loan Specific
           vehicle_make: loanData.vehicleMake,
           vehicle_model: loanData.vehicleModel,
           vehicle_year: loanData.vehicleYear,
           vehicle_type: loanData.vehicleType, // 'new', 'used', 'certified_pre_owned'
           
           // Application Context
           application_channel: loanData.applicationChannel, // 'online', 'branch', 'phone', 'mobile_app'
           referral_source: loanData.referralSource,
           co_applicant: loanData.hasCoApplicant,
           
           // Lead Quality
           pre_qualified: loanData.preQualified,
           documentation_complete: loanData.documentationComplete,
           approval_likelihood: loanData.approvalLikelihood // 'high', 'medium', 'low'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

---

### Travel & Hospitality Properties

#### Hotel Booking Event
```html
<script>
function trackHotelBooking(bookingData) {
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: 'purchase',
       label: 'Hotel Booking',
       value: bookingData.totalPrice,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Booking Details
           hotel_name: bookingData.hotelName,
           hotel_brand: bookingData.hotelBrand,
           star_rating: bookingData.starRating,
           check_in_date: bookingData.checkInDate,
           check_out_date: bookingData.checkOutDate,
           nights_stay: bookingData.nightsStay,
           
           // Room Details
           room_type: bookingData.roomType, // 'standard', 'deluxe', 'suite', 'presidential'
           number_of_rooms: bookingData.numberOfRooms,
           guests_total: bookingData.guestsTotal,
           adults: bookingData.adults,
           children: bookingData.children,
           
           // Location
           destination_city: bookingData.destinationCity,
           destination_country: bookingData.destinationCountry,
           hotel_location_type: bookingData.locationtype, // 'city_center', 'airport', 'beach', 'business_district'
           
           // Pricing
           room_rate_per_night: bookingData.roomRatePerNight,
           total_room_cost: bookingData.totalRoomCost,
           taxes_fees: bookingData.taxesFees,
           total_price: bookingData.totalPrice,
           currency: bookingData.currency,
           
           // Booking Context
           booking_channel: bookingData.bookingChannel, // 'direct', 'ota', 'travel_agent', 'mobile_app'
           advance_booking_days: bookingData.advanceBookingDays,
           booking_source: bookingData.bookingSource,
           promotion_code: bookingData.promotionCode,
           
           // Travel Purpose
           trip_purpose: bookingData.tripPurpose, // 'business', 'leisure', 'family', 'romantic'
           traveler_type: bookingData.travelerType, // 'solo', 'couple', 'family', 'group'
           
           // Amenities & Add-ons
           breakfast_included: bookingData.breakfastIncluded,
           wifi_included: bookingData.wifiIncluded,
           parking_included: bookingData.parkingIncluded,
           cancellation_policy: bookingData.cancellationPolicy // 'free', 'partial', 'non_refundable'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## Dynamic Property Implementation

### JavaScript Function for Dynamic Properties

```html
<script>
// Universal event tracking function with dynamic properties
function trackEventWithProperties(eventType, eventLabel, customProperties, monetaryValue) {
    var options = {
       account: '000000000000000000001234',
       event: eventType,
       label: eventLabel,
       ignore_pageview: 1,
       use_session: 1,
       properties: customProperties || {}
    };
    
    // Add monetary value if provided
    if (monetaryValue) {
        options.value = monetaryValue;
    }
    
    // Add timestamp and session info
    options.properties.timestamp = new Date().toISOString();
    options.properties.page_url = window.location.pathname;
    options.properties.referrer = document.referrer;
    
    (function() {
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Usage examples:
trackEventWithProperties('purchase', 'Product Purchase', {
    product_name: 'Wireless Headphones',
    brand: 'TechBrand',
    color: 'Black',
    price: 99.99
}, 99.99);

trackEventWithProperties('microconversion', 'Insurance Quote', {
    insurance_type: 'auto',
    vehicle_make: 'Toyota',
    vehicle_model: 'Camry',
    coverage_level: 'standard'
});
</script>
```

## Property Best Practices

### 1. **Consistent Naming Conventions**
- Use snake_case for property names: `product_name` not `productName`
- Be descriptive but concise: `vehicle_make` not `car_manufacturer_brand`
- Use consistent values: `'yes'/'no'` or `true/false`, not mixed

### 2. **Data Types and Formats**
```javascript
properties: {
    // Strings
    product_name: 'Wireless Headphones',
    category: 'Electronics',
    
    // Numbers
    price: 99.99,
    quantity: 2,
    
    // Booleans
    discount_applied: true,
    free_shipping: false,
    
    // Dates (ISO format)
    purchase_date: '2024-07-24T10:30:00Z',
    
    // Arrays (for multiple values)
    categories: ['Electronics', 'Audio', 'Wireless'],
    colors_available: ['Black', 'White', 'Silver']
}
```

### 3. **Property Categories and Organization**

| Category | Examples | Purpose |
|----------|----------|---------|
| **Product/Service** | `product_name`, `category`, `brand`, `model` | Core item identification |
| **Customer** | `customer_type`, `age_group`, `membership_level` | User segmentation |
| **Transaction** | `payment_method`, `discount_applied`, `shipping_method` | Purchase context |
| **Technical** | `device_type`, `browser`, `page_url`, `referrer` | Technical context |
| **Business** | `campaign`, `channel`, `lead_source`, `conversion_type` | Marketing attribution |

### 4. **Industry-Specific Property Standards**

#### E-commerce Standard Properties
```javascript
properties: {
    // Product Identification
    product_id: 'SKU-12345',
    product_name: 'Product Name',
    category: 'Main Category',
    subcategory: 'Sub Category',
    brand: 'Brand Name',
    
    // Product Attributes
    color: 'Black',
    size: 'Medium',
    material: 'Cotton',
    
    // Pricing
    price: 99.99,
    currency: 'USD',
    discount_percentage: 20,
    
    // Inventory
    stock_level: 'in_stock', // 'in_stock', 'low_stock', 'out_of_stock'
    quantity_available: 150
}
```

#### Insurance Standard Properties
```javascript
properties: {
    // Policy Identification
    insurance_type: 'auto', // 'auto', 'home', 'life', 'health'
    coverage_level: 'standard', // 'basic', 'standard', 'premium'
    policy_duration: '12_months',
    
    // Vehicle (Auto Insurance)
    vehicle_make: 'Toyota',
    vehicle_model: 'Camry',
    vehicle_year: 2020,
    vehicle_type: 'sedan',
    
    // Coverage Details
    coverage_amount: 100000,
    deductible: 500,
    premium_amount: 1200
}
```

## Advanced Property Techniques

### Conditional Properties Based on Context

```html
<script>
function getContextualProperties(eventType, baseData) {
    var properties = {
        // Always include base properties
        timestamp: new Date().toISOString(),
        page_url: window.location.pathname,
        user_agent: navigator.userAgent.substring(0, 100), // Truncated for privacy
        screen_resolution: screen.width + 'x' + screen.height
    };
    
    // Add event-specific properties
    if (eventType === 'purchase') {
        properties.transaction_id = 'TXN-' + Date.now();
        properties.payment_processed = true;
    }
    
    if (eventType === 'microconversion') {
        properties.conversion_step = baseData.step || 1;
        properties.funnel_position = baseData.funnelPosition || 'unknown';
    }
    
    // Add device context
    properties.device_type = /Mobile|Android|iPhone|iPad/.test(navigator.userAgent) ? 'mobile' : 'desktop';
    
    // Add time context
    var now = new Date();
    properties.hour_of_day = now.getHours();
    properties.day_of_week = now.getDay(); // 0 = Sunday
    properties.is_weekend = (now.getDay() === 0 || now.getDay() === 6);
    
    // Merge with custom properties
    return Object.assign(properties, baseData.customProperties || {});
}

// Usage
function trackAdvancedEvent(eventType, eventLabel, customData) {
    var properties = getContextualProperties(eventType, customData);
    
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: eventType,
       label: eventLabel,
       ignore_pageview: 1,
       use_session: 1,
       properties: properties
    };
    
    if (customData.value) options.value = customData.value;
    
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### A/B Testing Integration with Properties

```html
<script>
// A/B Testing with Properties
function trackWithExperiment(eventType, eventLabel, experimentData, customProperties) {
    var properties = Object.assign({
        // Experiment tracking
        experiment_name: experimentData.experimentName,
        variant: experimentData.variant,
        experiment_id: experimentData.experimentId,
        
        // User cohort information
        user_cohort: experimentData.userCohort,
        traffic_allocation: experimentData.trafficAllocation
    }, customProperties || {});
    
    (function() {
    var options = {
       account: '000000000000000000001234',
       event: eventType,
       label: eventLabel,
       ignore_pageview: 1,
       use_session: 1,
       properties: properties
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Example usage
trackWithExperiment('microconversion', 'Button Click', {
    experimentName: 'checkout_button_color',
    variant: 'green_button',
    experimentId: 'EXP-001',
    userCohort: 'new_users',
    trafficAllocation: 50
}, {
    button_position: 'header',
    page_type: 'product_detail'
});
</script>
```

## Property Analytics Benefits

### 1. **Detailed Segmentation**
- Analyze performance by any property combination
- Create custom user segments based on behavior
- Compare conversion rates across different attributes

### 2. **Advanced Attribution**
- Multi-dimensional attribution modeling
- Understand which product attributes drive sales
- Identify high-value customer characteristics

### 3. **Personalization Insights**
- Understand preferences by user segment
- Optimize product recommendations
- Tailor marketing messages based on behavior patterns

### 4. **Business Intelligence**
- Track business KPIs with granular detail
- Monitor trends in product attributes
- Identify opportunities for product development

## Implementation Checklist

### Planning Phase
- [ ] Define property taxonomy for your industry
- [ ] Establish naming conventions
- [ ] Identify key business questions properties will answer
- [ ] Map properties to existing data sources

### Development Phase
- [ ] Create property collection functions
- [ ] Implement error handling for missing properties
- [ ] Add validation for property data types
- [ ] Test property collection across different scenarios

### Testing Phase
- [ ] Verify properties are collected correctly
- [ ] Test with various browsers and devices
- [ ] Validate data accuracy in analytics dashboard
- [ ] Check performance impact of property collection

### Maintenance Phase
- [ ] Regular property usage review
- [ ] Update properties as business needs evolve
- [ ] Monitor property data quality
- [ ] Train team on property analysis techniques

## Common Property Mistakes to Avoid

### ❌ **Too Many Properties**
Avoid overwhelming events with unnecessary properties. Focus on actionable data.

### ❌ **Inconsistent Values**
```javascript
// Bad: Inconsistent formatting
properties: {
    color: 'Blue',        // Capitalized
    size: 'medium',       // Lowercase
    available: 'Yes'      // String instead of boolean
}

// Good: Consistent formatting  
properties: {
    color: 'blue',        // Lowercase
    size: 'medium',       // Lowercase  
    available: true       // Boolean
}
```

### ❌ **Personal Data in Properties**
Never include personal identifiable information in properties:
```javascript
// Bad: Contains PII
properties: {
    customer_email: 'john@example.com',
    customer_phone: '+1234567890'
}

// Good: Non-identifying data
properties: {
    customer_type: 'premium',
    customer_segment: 'high_value'
}
```

### ❌ **Dynamic Property Names**
Avoid creating property names dynamically as it makes analysis difficult:
```javascript
// Bad: Dynamic property names
properties: {
    'color_' + productColor: true,
    'size_' + productSize: true
}

// Good: Consistent property names
properties: {
    color: productColor,
    size: productSize
}
```

## Summary

Event Properties transform basic event tracking into rich, contextual analytics that provide deep business insights. By implementing properties strategically:

- **Capture Context**: Understand not just what happened, but how and why
- **Enable Segmentation**: Analyze performance across multiple dimensions  
- **Drive Decisions**: Make data-driven decisions with detailed insights
- **Optimize Performance**: Identify high-performing attributes and characteristics

Properties are the key to unlocking the full potential of your analytics, transforming simple event counts into actionable business intelligence that drives growth and optimization.