# SaaS Metrics Dashboard & Analytics Setup

## Complete SaaS Analytics Implementation

This guide provides comprehensive tracking for SaaS companies using Sealmetrics' privacy-first analytics to monitor user onboarding, feature usage, churn indicators, and product-led growth metrics.

## Core SaaS Event Tracking

### 1. User Registration & Signup

```html
<script>
function trackUserSignup(signupData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'User Signup',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Registration details
           signup_method: signupData.method, // 'email', 'google', 'github', 'sso'
           user_type: signupData.userType, // 'individual', 'team', 'enterprise'
           plan_selected: signupData.planSelected, // 'free', 'starter', 'pro', 'enterprise'
           
           // Company information
           company_size: signupData.companySize, // '1-10', '11-50', '51-200', '200+'
           industry: signupData.industry,
           use_case: signupData.useCase,
           
           // Marketing attribution
           signup_source: signupData.source, // 'organic', 'paid', 'referral', 'direct'
           campaign: signupData.campaign,
           referrer: signupData.referrer,
           
           // Context
           trial_length: signupData.trialLength, // days
           onboarding_flow: signupData.onboardingFlow, // 'standard', 'guided', 'self_serve'
           
           // Technical context
           signup_page: window.location.pathname,
           device_type: /Mobile|Android|iPhone|iPad/.test(navigator.userAgent) ? 'mobile' : 'desktop',
           signup_time: new Date().toISOString()
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### 2. Trial Activation & Onboarding

```html
<script>
function trackTrialActivation(activationData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Trial Activated',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Trial details
           trial_plan: activationData.trialPlan,
           trial_duration_days: activationData.trialDuration,
           features_included: activationData.featuresIncluded,
           
           // User setup
           setup_completed: activationData.setupCompleted,
           profile_completion: activationData.profileCompletion, // percentage
           team_members_invited: activationData.teamMembersInvited,
           
           // Onboarding progress
           onboarding_steps_completed: activationData.onboardingStepsCompleted,
           onboarding_completion_rate: activationData.onboardingCompletionRate,
           tutorial_completed: activationData.tutorialCompleted,
           
           // First actions
           first_project_created: activationData.firstProjectCreated,
           first_data_imported: activationData.firstDataImported,
           first_integration_connected: activationData.firstIntegrationConnected,
           
           // Time to activation
           signup_to_activation_hours: activationData.signupToActivationHours,
           activation_method: activationData.activationMethod // 'email_verification', 'phone_verification', 'admin_approval'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### 3. Feature Usage Tracking

```html
<script>
function trackFeatureUsage(featureData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'Feature Usage',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Feature identification
           feature_name: featureData.featureName,
           feature_category: featureData.featureCategory, // 'core', 'advanced', 'premium'
           feature_type: featureData.featureType, // 'creation', 'analysis', 'collaboration', 'integration'
           
           // Usage context
           user_plan: featureData.userPlan,
           user_role: featureData.userRole, // 'owner', 'admin', 'member', 'viewer'
           days_since_signup: featureData.daysSinceSignup,
           usage_frequency: featureData.usageFrequency, // 'first_time', 'occasional', 'regular', 'power_user'
           
           // Feature interaction
           session_duration_minutes: featureData.sessionDuration,
           actions_performed: featureData.actionsPerformed,
           data_processed_items: featureData.dataProcessed,
           
           // Feature success indicators
           task_completed: featureData.taskCompleted,
           result_exported: featureData.resultExported,
           result_shared: featureData.resultShared,
           
           // User experience
           help_accessed: featureData.helpAccessed,
           error_encountered: featureData.errorEncountered,
           feedback_provided: featureData.feedbackProvided,
           
           // Business context
           feature_tier: featureData.featureTier, // 'free', 'paid', 'enterprise'
           billing_impact: featureData.billingImpact, // usage-based billing
           collaboration_involved: featureData.collaborationInvolved
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Auto-track feature usage on key interactions
document.addEventListener('click', function(e) {
    const featureElement = e.target.closest('[data-feature]');
    if (featureElement) {
        const featureName = featureElement.getAttribute('data-feature');
        trackFeatureUsage({
            featureName: featureName,
            featureCategory: featureElement.getAttribute('data-feature-category') || 'core',
            userPlan: window.userPlan || 'unknown',
            daysSinceSignup: window.daysSinceSignup || 0
        });
    }
});
</script>
```

### 4. Subscription Events

```html
<script>
function trackSubscriptionEvent(subscriptionData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: subscriptionData.eventType, // 'purchase' for upgrades, 'microconversion' for others
       label: subscriptionData.eventLabel,
       value: subscriptionData.monthlyValue,
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Subscription details
           subscription_action: subscriptionData.action, // 'upgrade', 'downgrade', 'cancel', 'reactivate'
           from_plan: subscriptionData.fromPlan,
           to_plan: subscriptionData.toPlan,
           billing_cycle: subscriptionData.billingCycle, // 'monthly', 'annual'
           
           // Pricing
           monthly_value: subscriptionData.monthlyValue,
           annual_value: subscriptionData.annualValue,
           price_change: subscriptionData.priceChange,
           
           // Plan features
           user_seats_change: subscriptionData.userSeatsChange,
           storage_change: subscriptionData.storageChange,
           features_gained: subscriptionData.featuresGained,
           features_lost: subscriptionData.featuresLost,
           
           // Customer context
           customer_lifetime_months: subscriptionData.lifetimeMonths,
           previous_plan_duration: subscriptionData.previousPlanDuration,
           total_revenue_to_date: subscriptionData.totalRevenue,
           
           // Conversion context
           trigger_event: subscriptionData.triggerEvent, // 'usage_limit', 'feature_request', 'sales_contact'
           discount_applied: subscriptionData.discountApplied,
           discount_code: subscriptionData.discountCode,
           
           // Timing
           trial_to_paid_days: subscriptionData.trialToPaidDays,
           upgrade_reason: subscriptionData.upgradeReason,
           
           // Payment
           payment_method: subscriptionData.paymentMethod,
           payment_success: subscriptionData.paymentSuccess
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Example usage for different subscription events
function trackUpgrade(upgradeData) {
    trackSubscriptionEvent({
        eventType: 'purchase',
        eventLabel: 'Plan Upgrade',
        action: 'upgrade',
        monthlyValue: upgradeData.newMonthlyValue,
        ...upgradeData
    });
}

function trackCancellation(cancellationData) {
    trackSubscriptionEvent({
        eventType: 'microconversion',
        eventLabel: 'Subscription Cancelled',
        action: 'cancel',
        ...cancellationData
    });
}
</script>
```

### 5. User Engagement & Activity

```html
<script>
function trackUserActivity(activityData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'User Activity',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Activity metrics
           session_duration_minutes: activityData.sessionDuration,
           pages_visited: activityData.pagesVisited,
           actions_performed: activityData.actionsPerformed,
           features_used: activityData.featuresUsed.length,
           feature_list: activityData.featuresUsed,
           
           // Engagement indicators
           data_created: activityData.dataCreated,
           data_modified: activityData.dataModified,
           collaborations_initiated: activityData.collaborationsInitiated,
           integrations_used: activityData.integrationsUsed,
           
           // User context
           user_segment: activityData.userSegment, // 'new', 'growing', 'established', 'power_user'
           plan_type: activityData.planType,
           days_since_last_activity: activityData.daysSinceLastActivity,
           weekly_active_days: activityData.weeklyActiveDays,
           
           // Product adoption
           core_features_adopted: activityData.coreFeaturesAdopted,
           advanced_features_adopted: activityData.advancedFeaturesAdopted,
           onboarding_completion: activityData.onboardingCompletion,
           
           // Business value indicators
           projects_created: activityData.projectsCreated,
           reports_generated: activityData.reportsGenerated,
           api_calls_made: activityData.apiCallsMade,
           
           // Satisfaction indicators
           support_tickets_created: activityData.supportTicketsCreated,
           feedback_submitted: activityData.feedbackSubmitted,
           nps_score: activityData.npsScore
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Track activity at session end or periodically
window.addEventListener('beforeunload', function() {
    if (window.sessionActivityData) {
        trackUserActivity(window.sessionActivityData);
    }
});

// Track activity every 10 minutes for long sessions
setInterval(function() {
    if (window.sessionActivityData) {
        trackUserActivity(window.sessionActivityData);
        // Reset counters for next interval
        window.sessionActivityData.actionsPerformed = 0;
        window.sessionActivityData.pagesVisited = 0;
    }
}, 600000); // 10 minutes
</script>
```

## Churn Prediction & Analysis

### Early Warning Indicators

```html
<script>
function trackChurnIndicators(churnData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'Churn Risk Assessment',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Usage decline indicators
           activity_decline_percentage: churnData.activityDecline,
           days_since_last_login: churnData.daysSinceLastLogin,
           feature_usage_decline: churnData.featureUsageDecline,
           session_frequency_change: churnData.sessionFrequencyChange,
           
           // Engagement red flags
           support_tickets_increase: churnData.supportTicketsIncrease,
           error_rate_increase: churnData.errorRateIncrease,
           failed_actions_increase: churnData.failedActionsIncrease,
           
           // Business indicators
           plan_downgrades: churnData.planDowngrades,
           seat_reductions: churnData.seatReductions,
           integration_disconnections: churnData.integrationDisconnections,
           
           // Behavioral signals
           billing_page_visits: churnData.billingPageVisits,
           cancellation_page_visits: churnData.cancellationPageVisits,
           competitor_research: churnData.competitorResearch,
           export_data_frequency: churnData.exportDataFrequency,
           
           // Account health
           team_activity_decline: churnData.teamActivityDecline,
           admin_engagement_decline: churnData.adminEngagementDecline,
           onboarding_abandonment: churnData.onboardingAbandonment,
           
           // Risk scoring
           churn_risk_score: churnData.churnRiskScore, // 1-100
           risk_category: churnData.riskCategory, // 'low', 'medium', 'high', 'critical'
           
           // Customer success context
           last_customer_success_interaction: churnData.lastCSInteraction,
           satisfaction_score_trend: churnData.satisfactionTrend,
           renewal_date_proximity: churnData.renewalDateProximity
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## Product-Led Growth Metrics

### Viral & Referral Tracking

```html
<script>
function trackViralActivity(viralData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Viral Activity',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Viral action
           viral_action: viralData.action, // 'invite_sent', 'share_created', 'referral_made'
           viral_channel: viralData.channel, // 'email', 'social', 'link', 'in_app'
           
           // Invitation details
           invitations_sent: viralData.invitationsSent,
           invitation_method: viralData.invitationMethod,
           custom_message_included: viralData.customMessageIncluded,
           
           // Share details
           content_shared: viralData.contentShared, // 'dashboard', 'report', 'project'
           share_permissions: viralData.sharePermissions, // 'view', 'edit', 'admin'
           public_share: viralData.publicShare,
           
           // Referral program
           referral_code_used: viralData.referralCodeUsed,
           referral_incentive: viralData.referralIncentive,
           referrer_reward: viralData.referrerReward,
           
           // User context
           user_tenure_days: viralData.userTenureDays,
           user_plan: viralData.userPlan,
           user_satisfaction: viralData.userSatisfaction,
           
           // Viral coefficient tracking
           network_size: viralData.networkSize,
           previous_viral_actions: viralData.previousViralActions,
           viral_loop_stage: viralData.viralLoopStage // 'initial', 'secondary', 'tertiary'
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

### Product Adoption Milestones

```html
<script>
function trackAdoptionMilestone(milestoneData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'microconversion',
       label: 'Adoption Milestone',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Milestone identification
           milestone_name: milestoneData.milestoneName,
           milestone_type: milestoneData.milestoneType, // 'onboarding', 'usage', 'value', 'expansion'
           milestone_category: milestoneData.category, // 'first_value', 'habit_formation', 'expansion'
           
           // Milestone details
           milestone_value: milestoneData.value, // numeric value of milestone
           milestone_unit: milestoneData.unit, // 'projects', 'reports', 'api_calls', 'collaborators'
           
           // User journey
           days_to_milestone: milestoneData.daysToMilestone,
           milestone_sequence: milestoneData.milestoneSequence, // which milestone in the journey
           previous_milestone: milestoneData.previousMilestone,
           
           // Context
           user_plan_at_milestone: milestoneData.planAtMilestone,
           team_size_at_milestone: milestoneData.teamSizeAtMilestone,
           features_used_to_reach: milestoneData.featuresUsedToReach,
           
           // Success indicators
           milestone_impact_on_retention: milestoneData.retentionImpact,
           milestone_impact_on_expansion: milestoneData.expansionImpact,
           
           // Business value
           revenue_at_milestone: milestoneData.revenueAtMilestone,
           usage_intensity: milestoneData.usageIntensity, // 'light', 'moderate', 'heavy'
           
           // Predictive indicators
           next_milestone_prediction: milestoneData.nextMilestonePrediction,
           churn_risk_after_milestone: milestoneData.churnRiskAfterMilestone,
           upgrade_probability: milestoneData.upgradeProbability
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}

// Example milestone triggers
function checkAdoptionMilestones(userActivity) {
    // First project created
    if (userActivity.projectsCreated === 1 && !userActivity.milestonesReached.includes('first_project')) {
        trackAdoptionMilestone({
            milestoneName: 'first_project_created',
            milestoneType: 'onboarding',
            value: 1,
            unit: 'projects',
            daysToMilestone: userActivity.daysSinceSignup
        });
    }
    
    // Power user threshold (100 API calls)
    if (userActivity.totalApiCalls >= 100 && !userActivity.milestonesReached.includes('power_user')) {
        trackAdoptionMilestone({
            milestoneName: 'power_user_threshold',
            milestoneType: 'usage',
            value: userActivity.totalApiCalls,
            unit: 'api_calls',
            daysToMilestone: userActivity.daysSinceSignup
        });
    }
}
</script>
```

## Advanced SaaS Analytics

### A/B Testing Integration

```html
<script>
function trackSaaSExperiment(experimentData) {
    (function() {
    var options = {
       account: 'YOUR_ACCOUNT_ID_HERE',
       event: 'custom',
       label: 'A/B Test Interaction',
       ignore_pageview: 1,
       use_session: 1,
       properties: {
           // Experiment details
           experiment_name: experimentData.experimentName,
           experiment_id: experimentData.experimentId,
           variant: experimentData.variant,
           
           // User context
           user_segment: experimentData.userSegment,
           user_plan: experimentData.userPlan,
           user_tenure: experimentData.userTenure,
           
           // Interaction
           interaction_type: experimentData.interactionType, // 'view', 'click', 'conversion'
           feature_affected: experimentData.featureAffected,
           
           // Outcome
           conversion_achieved: experimentData.conversionAchieved,
           conversion_value: experimentData.conversionValue,
           
           // Statistical context
           confidence_level: experimentData.confidenceLevel,
           statistical_significance: experimentData.statisticalSignificance
       }
    };
    var url="//app.sealmetrics.com/tag/v2/tracker";function loadScript(callback){var script=document.createElement("script");script.src=url;script.async=true;script.onload=function(){if(typeof callback==="function"){callback();}};script.onerror=function(){console.error("Error loading script: "+url);};document.getElementsByTagName("head")[0].appendChild(script);}loadScript(function(){options.id=Math.floor((Math.random()*999)+1);if(window.sm){var instance=new window.sm(options);instance.track(options.event);}else{console.error("sm2 plugin is not available");}});
    })();
}
</script>
```

## SaaS Analytics Dashboard Configuration

### Key Metrics to Track

#### 1. **Acquisition Metrics**
- **Sign-up Rate**: Track registration conversions
- **Activation Rate**: Users who complete onboarding
- **Time to First Value**: Speed of initial value delivery
- **Source Attribution**: Which channels drive quality users

#### 2. **Engagement Metrics**
- **Daily/Weekly/Monthly Active Users (DAU/WAU/MAU)**
- **Feature Adoption Rate**: Core feature usage
- **Session Duration**: Time spent in application
- **User Journey Analysis**: Path through the product

#### 3. **Retention Metrics**
- **Cohort Retention**: User retention by signup cohort
- **Churn Rate**: Monthly/annual churn tracking
- **Customer Lifetime Value (CLV)**
- **Net Revenue Retention (NRR)**

#### 4. **Growth Metrics**
- **Monthly Recurring Revenue (MRR)**
- **Annual Recurring Revenue (ARR)**
- **Average Revenue Per User (ARPU)**
- **Expansion Revenue**: Upsells and cross-sells

#### 5. **Product-Led Growth Metrics**
- **Viral Coefficient**: User-driven growth
- **Product Qualified Leads (PQLs)**
- **Feature Usage Depth**: Advanced feature adoption
- **Self-Service Conversion Rate**

### Custom Dashboard Views

```javascript
// Dashboard configuration for different stakeholders
const dashboardConfigs = {
    // Executive Dashboard
    executive: {
        metrics: ['MRR', 'ARR', 'Churn Rate', 'CAC', 'LTV'],
        timeframe: 'monthly',
        segments: ['plan_type', 'company_size']
    },
    
    // Product Team Dashboard
    product: {
        metrics: ['Feature Adoption', 'User Engagement', 'Onboarding Completion', 'Churn by Feature'],
        timeframe: 'weekly',
        segments: ['user_segment', 'feature_usage']
    },
    
    // Customer Success Dashboard
    customer_success: {
        metrics: ['Health Score', 'Usage Trends', 'Support Tickets', 'NPS'],
        timeframe: 'daily',
        segments: ['risk_level', 'plan_type', 'tenure']
    },
    
    // Marketing Dashboard
    marketing: {
        metrics: ['Acquisition', 'Activation', 'Attribution', 'CAC by Channel'],
        timeframe: 'weekly',
        segments: ['traffic_source', 'campaign', 'user_type']
    }
};
```

### Automated Alerts & Monitoring

```html
<script>
// Set up automated monitoring for key SaaS metrics
function setupSaaSMonitoring() {
    // Monitor for churn risk indicators
    if (window.userMetrics && window.userMetrics.churnRiskScore > 70) {
        trackChurnIndicators({
            churnRiskScore: window.userMetrics.churnRiskScore,
            riskCategory: 'high',
            triggerEvent: 'automated_monitoring'
        });
    }
    
    // Monitor for expansion opportunities
    if (window.userMetrics && window.userMetrics.usageGrowth > 50) {
        trackAdoptionMilestone({
            milestoneName: 'expansion_opportunity',
            milestoneType: 'expansion',
            usageGrowth: window.userMetrics.usageGrowth
        });
    }
}

// Run monitoring checks periodically
setInterval(setupSaaSMonitoring, 3600000); // Every hour
</script>
```

This comprehensive SaaS analytics setup provides complete visibility into user behavior, product adoption, churn indicators, and growth metrics while maintaining privacy compliance through Sealmetrics' consentless tracking approach.