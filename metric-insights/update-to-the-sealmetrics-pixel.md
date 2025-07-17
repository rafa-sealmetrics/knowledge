---
title: Update to the SealMetrics Pixel
description: ''
slug: update-to-the-sealmetrics-pixel
---
[Skip to main content](#main-content)![Image](update-to-the-sealmetrics-pixel/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Metric Insights](https://help.sealmetrics.com/en/collections/10013737-metric-insights)We’re excited to announce a significant update to the SealMetrics pixel, designed to improve functionality and give users more flexibility in tracking events. This article outlines the differences between the old and new pixels, explains why you should update, and provides detailed implementation examples.

Why Update to the New Pixel?

The new SealMetrics pixel introduces several improvements over the previous version:

Improved Customization:The new pixel allows you to control whether a pageview event is triggered automatically when tracking conversions or micro-conversions. This provides more accurate event tracking, especially when a pageview should not be logged.Future Updates:The old pixel will no longer receive updates or support. To take advantage of ongoing enhancements and new features, we recommend transitioning to the new version.Enhanced Error Handling:The new pixel includes better error reporting for script loading issues, ensuring smoother implementation.

Improved Customization:The new pixel allows you to control whether a pageview event is triggered automatically when tracking conversions or micro-conversions. This provides more accurate event tracking, especially when a pageview should not be logged.

Improved Customization:The new pixel allows you to control whether a pageview event is triggered automatically when tracking conversions or micro-conversions. This provides more accurate event tracking, especially when a pageview should not be logged.

Future Updates:The old pixel will no longer receive updates or support. To take advantage of ongoing enhancements and new features, we recommend transitioning to the new version.

Future Updates:The old pixel will no longer receive updates or support. To take advantage of ongoing enhancements and new features, we recommend transitioning to the new version.

Enhanced Error Handling:The new pixel includes better error reporting for script loading issues, ensuring smoother implementation.

Enhanced Error Handling:The new pixel includes better error reporting for script loading issues, ensuring smoother implementation.



Comparison: Old Pixel vs. New Pixel

Old Pixel

Here is an example of the old pixel:





When implemented, this version automatically triggers a page view event but lacks flexibility in configuring specific event-tracking behavior.



New Pixel

The new pixel simplifies configuration and adds advanced options for event tracking. Here’s the updated version:



Default Pageview Tracking





Tracking Conversions with the New Pixel

One of the main differences in the new pixel is how conversion events are handled. By default, the new pixel doesnottrigger a pageview event when tracking conversions. This behavior can be adjusted based on your needs.



Example 1: Conversion Without Pageview

To track a conversion without logging a pageview, setignore_pageviewto1:





Example 2: Conversion with Pageview

If you prefer to include a page view event along with the conversion, simply omit theignore_pageviewparameter:





Summary

The new pixel provides greater flexibility and customization options.Users are encouraged to update to the new pixel, as the old version will no longer be updated or supported.By default, the new pixel does not trigger a pageview for conversion events, but this behavior can be modified.

The new pixel provides greater flexibility and customization options.

The new pixel provides greater flexibility and customization options.

Users are encouraged to update to the new pixel, as the old version will no longer be updated or supported.

Users are encouraged to update to the new pixel, as the old version will no longer be updated or supported.

By default, the new pixel does not trigger a pageview for conversion events, but this behavior can be modified.

By default, the new pixel does not trigger a pageview for conversion events, but this behavior can be modified.

For any questions or assistance with updating your pixel, please get in touch with our support team.

[How SuperPrivacy Tracking Works](https://help.sealmetrics.com/en/articles/9667399-how-superprivacy-tracking-works)[How to track REACT sites:](https://help.sealmetrics.com/en/articles/9667468-how-to-track-react-sites)[How to track SPA sites:](https://help.sealmetrics.com/en/articles/9667469-how-to-track-spa-sites)[How to track Ajax Forms:](https://help.sealmetrics.com/en/articles/9667471-how-to-track-ajax-forms)[How to Measure Conversions and Micro-Conversions](https://help.sealmetrics.com/en/articles/10208596-how-to-measure-conversions-and-micro-conversions)[SealMetrics Help Center](/en/)Company

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