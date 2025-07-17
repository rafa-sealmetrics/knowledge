---
title: What is gtm-msr.appspot.com and How to Prevent It from Triggering Tags in GTM
description: ''
slug: what-is-gtm-msr.appspot.com-and-how-to-prevent-it-from-triggering-tags-in-gtm
---
[Skip to main content](#main-content)![Image](what-is-gtm-msr.appspot.com-and-how-to-prevent-it-from-triggering-tags-in-gtm/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Metric Insights](https://help.sealmetrics.com/en/collections/10013737-metric-insights)

What is gtm-msr.appspot.com?

The domain gtm-msr.appspot.com is owned byGoogle Tag Manager (GTM). It appears when:

You or your team enterPreview Modein GTM.Google runsautomated scansorsecurity checkson your container.A tool or browser extension triggers a GTM render for testing/debugging.

You or your team enterPreview Modein GTM.

You or your team enterPreview Modein GTM.

Google runsautomated scansorsecurity checkson your container.

Google runsautomated scansorsecurity checkson your container.

A tool or browser extension triggers a GTM render for testing/debugging.

A tool or browser extension triggers a GTM render for testing/debugging.

This domaindoes not reflect real user traffic, but it can cause your tags to fire unintentionally, leading to:

False pageviewsPhantom conversionsPolluted analytics reports

False pageviews

False pageviews

Phantom conversions

Phantom conversions

Polluted analytics reports

Polluted analytics reports

Why It’s a Problem

If your GTM tags fire while loaded from gtm-msr.appspot.com, they may:

Trigger pixels (TikTok, Meta, Google Ads…) with fake hitsInflate events or conversions in GA4, Meta Ads Manager, or other platformsBreak attribution accuracy

Trigger pixels (TikTok, Meta, Google Ads…) with fake hits

Trigger pixels (TikTok, Meta, Google Ads…) with fake hits

Inflate events or conversions in GA4, Meta Ads Manager, or other platforms

Inflate events or conversions in GA4, Meta Ads Manager, or other platforms

Break attribution accuracy

Break attribution accuracy



How to Prevent Tags from Firing on gtm-msr.appspot.com

To ensure no tag fires when GTM is loaded from this domain, follow this method:



Step 1: Create a Blocking Variable

Go toVariablesin Google Tag Manager.ClickNew→ chooseCustom JavaScript Variable.Name it: IsNotGTMAppspotUse this code:

Go toVariablesin Google Tag Manager.

Go toVariablesin Google Tag Manager.

ClickNew→ chooseCustom JavaScript Variable.

ClickNew→ chooseCustom JavaScript Variable.

Name it: IsNotGTMAppspot

Name it: IsNotGTMAppspot

Use this code:

Use this code:

5. Save





Step 2: Add the Condition to All Triggers

For every trigger that launches tags (pageviews, clicks, events, etc.):

Open the trigger.Add this condition:

Open the trigger.

Open the trigger.

Add this condition:

Add this condition:

This tells GTM: “Only fire if the current hostname isnotgtm-msr.appspot.com.”





(Optional) Extra Safety for Custom HTML Tags

If you’re using Custom HTML tags, wrap the code inside this condition:



How to Test It

ClickPreviewin GTM.Confirm the URL becomes gtm-msr.appspot.com.Check thatno tags are firedduring the preview.If everything looks good,publish your container.

ClickPreviewin GTM.

ClickPreviewin GTM.

Confirm the URL becomes gtm-msr.appspot.com.

Confirm the URL becomes gtm-msr.appspot.com.

Check thatno tags are firedduring the preview.

Check thatno tags are firedduring the preview.

If everything looks good,publish your container.

If everything looks good,publish your container.





Problem

Solution

Tags firing from gtm-msr.appspot.com

Create a custom variable + add it as a blocking condition in all triggers

False hits in analytics

Filter by hostname or use conditional logic to restrict execution

Clean data = better decisions

✅ Stop pixel spam at the source



[Why Does GA4 Measure More Than Sealmetrics?](https://help.sealmetrics.com/en/articles/10006652-why-does-ga4-measure-more-than-sealmetrics)[Setting Up Trackers in Sealmetrics](https://help.sealmetrics.com/en/articles/10054456-setting-up-trackers-in-sealmetrics)[How to Measure Conversions and Micro-Conversions](https://help.sealmetrics.com/en/articles/10208596-how-to-measure-conversions-and-micro-conversions)[Google Tag Manager vs Direct Code](https://help.sealmetrics.com/en/articles/10213845-google-tag-manager-vs-direct-code)[What is gtm-msr.appspot.com?](https://help.sealmetrics.com/en/articles/11721807-what-is-gtm-msr-appspot-com)[SealMetrics Help Center](/en/)Company

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