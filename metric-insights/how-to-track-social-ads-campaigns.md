---
title: How to track Social Ads Campaigns
description: ''
slug: how-to-track-social-ads-campaigns
---
[Skip to main content](#main-content)![Image](how-to-track-social-ads-campaigns/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Metric Insights](https://help.sealmetrics.com/en/collections/10013737-metric-insights)Sealmetrics uses multiple methods to accurately track and attribute traffic coming from Meta Ads (Facebook and Instagram advertisements).

Two Primary Tracking Methods

Method 1: UTM Parameters

UTM parameters are custom tags that you can add to your Meta Ads URLs to track the performance of your campaigns. When you use UTM parameters in your Meta Ads campaigns, Sealmetrics will capture and display this information in your analytics dashboard.



How to implement UTM tracking:

Add UTM parameters to your ad destination URLsUse consistent naming conventions across campaignsEnsure all required parameters are included

Add UTM parameters to your ad destination URLs

Add UTM parameters to your ad destination URLs

Use consistent naming conventions across campaigns

Use consistent naming conventions across campaigns

Ensure all required parameters are included

Ensure all required parameters are included

Example UTM structure for Meta Ads:

Benefits of UTM tracking:

Complete campaign attributionDetailed performance insightsCustom campaign namingFull control over tracking parameters

Complete campaign attribution

Complete campaign attribution

Detailed performance insights

Detailed performance insights

Custom campaign naming

Custom campaign naming

Full control over tracking parameters

Full control over tracking parameters

Method 2: Facebook Click ID (fbclid)

When users click on your Meta Ads, Facebook automatically appends a unique identifier calledfbclidto your landing page URL. Sealmetrics automatically detects this parameter and attributes the traffic to Meta Ads.

How fbclid tracking works:

User clicks on your Meta AdFacebook automatically addsfbclidparameter to the URLSealmetrics detects the fbclid and identifies the traffic sourceTraffic is automatically categorized as coming from Meta Ads

User clicks on your Meta Ad

User clicks on your Meta Ad

Facebook automatically addsfbclidparameter to the URL

Facebook automatically addsfbclidparameter to the URL

Sealmetrics detects the fbclid and identifies the traffic source

Sealmetrics detects the fbclid and identifies the traffic source

Traffic is automatically categorized as coming from Meta Ads

Traffic is automatically categorized as coming from Meta Ads

Example URL with fbclid:

UTM Attribution vs. fbclid Attribution

When UTM Parameters Are Present

If your Meta Ads URLs include UTM parameters, Sealmetrics will use this information for attribution:

utm_source: facebook (or your custom source)utm_medium: cpc (or your custom medium)utm_campaign: Your specific campaign nameutm_term: Your specific keyword/audience targetingutm_content: Your ad variant identifier

utm_source: facebook (or your custom source)

utm_source: facebook (or your custom source)

utm_medium: cpc (or your custom medium)

utm_medium: cpc (or your custom medium)

utm_campaign: Your specific campaign name

utm_campaign: Your specific campaign name

utm_term: Your specific keyword/audience targeting

utm_term: Your specific keyword/audience targeting

utm_content: Your ad variant identifier

utm_content: Your ad variant identifier

When Only fbclid Is Present

When Sealmetrics detects fbclid without UTM parameters, the system automatically applies the following attribution:

utm_source: facebook-adsutm_medium: cpcutm_campaign: (not set)utm_term: (not set)

utm_source: facebook-ads

utm_source: facebook-ads

utm_medium: cpc

utm_medium: cpc

utm_campaign: (not set)

utm_campaign: (not set)

utm_term: (not set)

utm_term: (not set)

This automatic attribution ensures that all Meta Ads traffic is properly identified, even when UTM parameters are not manually configured.

Best Practices for Meta Ads Tracking

1. Use UTM Parameters for Detailed Tracking

For maximum insight into your campaign performance, always include UTM parameters in your Meta Ads URLs. This allows you to:

Track individual campaign performanceCompare different ad sets and creative variantsAnalyze audience segment effectivenessGenerate detailed ROI reports

Track individual campaign performance

Track individual campaign performance

Compare different ad sets and creative variants

Compare different ad sets and creative variants

Analyze audience segment effectiveness

Analyze audience segment effectiveness

Generate detailed ROI reports

Generate detailed ROI reports

2. Maintain Consistent Naming Conventions

Establish and follow consistent UTM naming conventions:

Use lowercase lettersReplace spaces with underscores or hyphensKeep names descriptive but conciseDocument your naming scheme for team consistency

Use lowercase letters

Use lowercase letters

Replace spaces with underscores or hyphens

Replace spaces with underscores or hyphens

Keep names descriptive but concise

Keep names descriptive but concise

Document your naming scheme for team consistency

Document your naming scheme for team consistency

3. Monitor Both Attribution Methods

Even when using UTM parameters, monitor your fbclid traffic to ensure:

No traffic is going untrackedUTM parameters are working correctlyAll Meta Ads traffic is being captured

No traffic is going untracked

No traffic is going untracked

UTM parameters are working correctly

UTM parameters are working correctly

All Meta Ads traffic is being captured

All Meta Ads traffic is being captured

Understanding Your Analytics Reports

Campaign Performance Analysis

With proper UTM implementation, you can analyze:

Campaign-level performance: Compare different Meta Ads campaignsCreative performance: Track which ad variants perform bestAudience insights: Understand which targeting parameters drive resultsCross-platform comparison: Compare Meta Ads performance with other channels

Campaign-level performance: Compare different Meta Ads campaigns

Campaign-level performance: Compare different Meta Ads campaigns

Creative performance: Track which ad variants perform best

Creative performance: Track which ad variants perform best

Audience insights: Understand which targeting parameters drive results

Audience insights: Understand which targeting parameters drive results

Cross-platform comparison: Compare Meta Ads performance with other channels

Cross-platform comparison: Compare Meta Ads performance with other channels

Traffic Source Identification

In your Sealmetrics dashboard, Meta Ads traffic will appear as:

With UTMs: Source shows your custom utm_source valuefbclid only: Source shows as "facebook-ads"Medium: Shows "cpc" or your custom utm_medium value

With UTMs: Source shows your custom utm_source value

With UTMs: Source shows your custom utm_source value

fbclid only: Source shows as "facebook-ads"

fbclid only: Source shows as "facebook-ads"

Medium: Shows "cpc" or your custom utm_medium value

Medium: Shows "cpc" or your custom utm_medium value

Troubleshooting Common Issues

Missing Campaign Data

If you see traffic with source "facebook-ads" but campaign shows "(not set)":

Check if UTM parameters are properly added to your ad URLsVerify UTM parameters are not being stripped by redirectsEnsure landing pages preserve URL parameters

Check if UTM parameters are properly added to your ad URLs

Check if UTM parameters are properly added to your ad URLs

Verify UTM parameters are not being stripped by redirects

Verify UTM parameters are not being stripped by redirects

Ensure landing pages preserve URL parameters

Ensure landing pages preserve URL parameters

Inconsistent Attribution

If attribution seems inconsistent:

Review your UTM naming conventionsCheck for URL shorteners that might strip parametersVerify that all team members are using the same UTM structure

Review your UTM naming conventions

Review your UTM naming conventions

Check for URL shorteners that might strip parameters

Check for URL shorteners that might strip parameters

Verify that all team members are using the same UTM structure

Verify that all team members are using the same UTM structure

Conclusion

Sealmetrics provides robust tracking for Meta Ads traffic through both UTM parameters and automatic fbclid detection. While fbclid ensures that no Meta Ads traffic goes untracked, implementing proper UTM parameters provides the detailed insights needed to optimize your advertising spend and improve campaign performance.

For the most comprehensive analytics, we recommend using UTM parameters on all your Meta Ads campaigns while relying on fbclid detection as a backup attribution method.

[How SuperPrivacy Tracking Works](https://help.sealmetrics.com/en/articles/9667399-how-superprivacy-tracking-works)[How to track Google Ads Campaigns:](https://help.sealmetrics.com/en/articles/9667466-how-to-track-google-ads-campaigns)[Understanding Referrer Loss and Direct Traffic in Sealmetrics](https://help.sealmetrics.com/en/articles/11125734-understanding-referrer-loss-and-direct-traffic-in-sealmetrics)[How SealMetrics Calculates SEO Traffic](https://help.sealmetrics.com/en/articles/11154410-how-sealmetrics-calculates-seo-traffic)[What is a TERM in SealMetrics?](https://help.sealmetrics.com/en/articles/11154456-what-is-a-term-in-sealmetrics)[SealMetrics Help Center](/en/)Company

Privacy PolicyDPATerms of UseData Privacy Audit

Privacy Policy

[Privacy Policy](https://legal.sealmetrics.com/privacy-notice)DPA

[DPA](https://legal.sealmetrics.com/DPA)Terms of Use

[Terms of Use](https://sealmetrics.com/terms-of-use/)Data Privacy Audit

[Data Privacy Audit](https://app.comply.org/attest/sealmetrics)Guides

Cookie Consent GuideSocial Media AuditCookieless & Google

Cookie Consent Guide

[Cookie Consent Guide](https://sealmetrics.com/mastering-the-cookie-consent-banner/)Social Media Audit

[Social Media Audit](https://sealmetrics.com/in-depth-analysis-of-social-media-privacy-policies/)Cookieless & Google

[Cookieless & Google](https://sealmetrics.com/how-google-is-navigating-the-cookieless-future/)Explore

Check out the live demoNewsletter

Check out the live demo

[Check out the live demo](https://app.sealmetrics.com/reports/cookieless/dashboard)Newsletter

[Newsletter](https://sealmetrics.com/privacy-marketing-newsletter/)