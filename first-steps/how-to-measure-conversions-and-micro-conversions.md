---
title: How to Measure Conversions and Micro-Conversions
description: ''
slug: how-to-measure-conversions-and-micro-conversions
---
[Skip to main content](#main-content)![Image](how-to-measure-conversions-and-micro-conversions/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[First Steps](https://help.sealmetrics.com/en/collections/10013519-first-steps)With the new SealMetrics pixel, you have complete control over measuring conversions and micro-conversions, ensuring accurate data collection while preventing unnecessary duplication of page view events. Every conversion or micro-conversion event must be linked to a pageview, but you can configure whether that pageview is triggered automatically or managed externally.



This guide explains how to configure your pixel for various use cases.



Key Configuration Options

Automatic Pageview Triggering: By default, the new pixel includes a pageview event when tracking conversions.Excluding Pageview from the Conversion Pixel: You can avoid triggering an additional pageview event by adding theignore_pageviewparameter.

Automatic Pageview Triggering: By default, the new pixel includes a pageview event when tracking conversions.

Automatic Pageview Triggering: By default, the new pixel includes a pageview event when tracking conversions.

Excluding Pageview from the Conversion Pixel: You can avoid triggering an additional pageview event by adding theignore_pageviewparameter.

Excluding Pageview from the Conversion Pixel: You can avoid triggering an additional pageview event by adding theignore_pageviewparameter.

This flexibility ensures your tracking setup is tailored to your needs and avoids double-counting pageviews.



Use Cases

1. Tracking a Button Click (Avoiding Duplicate Pageviews)

If you're measuring an event like a button click on a page where the pageview has already been recorded, you shoulddisable the pageview eventin the conversion pixel. This prevents counting two pageviews for the same session.

Here’s how to configure the pixel:





2. Tracking a Conversion (Including Pageview)

If you need to include a pageview when tracking a conversion (e.g., a purchase confirmation page), simplyomit theignore_pageviewparameter. This ensures the pageview and conversion are both tracked accurately.





How It Works

Default Behavior: The new pixel automatically tracks a pageview alongside any conversion or micro-conversion.Customizing Behavior: You can prevent the pageview from being triggered by addingignore_pageview: 1to the configuration.

Default Behavior: The new pixel automatically tracks a pageview alongside any conversion or micro-conversion.

Default Behavior: The new pixel automatically tracks a pageview alongside any conversion or micro-conversion.

Customizing Behavior: You can prevent the pageview from being triggered by addingignore_pageview: 1to the configuration.

Customizing Behavior: You can prevent the pageview from being triggered by addingignore_pageview: 1to the configuration.



Best Practices

Avoid Duplicate Pageviews:If you're tracking an event (like a button click) on a page where the pageview has already been logged, use theignore_pageviewparameter to avoid double-counting.Ensure Every Conversion Has a Pageview:Every conversion or micro-conversion needs to be associated with a pageview. If you exclude the pageview from the conversion pixel, ensure it has already been triggered elsewhere in your setup.

Avoid Duplicate Pageviews:If you're tracking an event (like a button click) on a page where the pageview has already been logged, use theignore_pageviewparameter to avoid double-counting.

Avoid Duplicate Pageviews:

If you're tracking an event (like a button click) on a page where the pageview has already been logged, use theignore_pageviewparameter to avoid double-counting.

If you're tracking an event (like a button click) on a page where the pageview has already been logged, use theignore_pageviewparameter to avoid double-counting.

If you're tracking an event (like a button click) on a page where the pageview has already been logged, use theignore_pageviewparameter to avoid double-counting.

Ensure Every Conversion Has a Pageview:Every conversion or micro-conversion needs to be associated with a pageview. If you exclude the pageview from the conversion pixel, ensure it has already been triggered elsewhere in your setup.

Ensure Every Conversion Has a Pageview:

Every conversion or micro-conversion needs to be associated with a pageview. If you exclude the pageview from the conversion pixel, ensure it has already been triggered elsewhere in your setup.

Every conversion or micro-conversion needs to be associated with a pageview. If you exclude the pageview from the conversion pixel, ensure it has already been triggered elsewhere in your setup.

Every conversion or micro-conversion needs to be associated with a pageview. If you exclude the pageview from the conversion pixel, ensure it has already been triggered elsewhere in your setup.



Where to find Event pixels:

![Image](how-to-measure-conversions-and-micro-conversions/Seal-Metrics-11-28-2024_06_39_AM.png)





[How SuperPrivacy Tracking Works](https://help.sealmetrics.com/en/articles/9667399-how-superprivacy-tracking-works)[How to track REACT sites:](https://help.sealmetrics.com/en/articles/9667468-how-to-track-react-sites)[How to track SPA sites:](https://help.sealmetrics.com/en/articles/9667469-how-to-track-spa-sites)[How to track Ajax Forms:](https://help.sealmetrics.com/en/articles/9667471-how-to-track-ajax-forms)[Update to the SealMetrics Pixel](https://help.sealmetrics.com/en/articles/10208561-update-to-the-sealmetrics-pixel)[SealMetrics Help Center](/en/)Company

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