---
title: Why do I see more conversions or revenue in Sealmetrics than in my ERP?
description: ''
slug: why-do-i-see-more-conversions-or-revenue-in-sealmetrics-than-in-my-erp?
---
[Skip to main content](#main-content)![Image](why-do-i-see-more-conversions-or-revenue-in-sealmetrics-than-in-my-erp?/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Metric Insights](https://help.sealmetrics.com/en/collections/10013737-metric-insights)This is a common and understandable question.



Sealmetrics uses avery simple and strict conversion pixel:



If the pixel is called, it counts. If it’s not called, it doesn’t.



That means:

Every time the conversion pixel URL is triggered, we count a conversion.We don’t filter for deduplication, user uniqueness, or match it with backend validations.We don’t access your ERP or checkout system—we only record the pixel event.

Every time the conversion pixel URL is triggered, we count a conversion.

Every time the conversion pixel URL is triggered, we count a conversion.

We don’t filter for deduplication, user uniqueness, or match it with backend validations.

We don’t filter for deduplication, user uniqueness, or match it with backend validations.

We don’t access your ERP or checkout system—we only record the pixel event.

We don’t access your ERP or checkout system—we only record the pixel event.



Common reasons for discrepancies:

Duplicate pixel firesIf a user refreshes the thank-you page, the pixel may fire again. This will count as a second conversion.Multiple user visits to confirmation pagesIf users revisit the confirmation URL (via email links, bookmarks, or back button), the pixel fires again.Pixel placed on the wrong URL(s)If the pixel is notexclusivelyon the final “thank you” page, it might be firing on other pages as well, leading to overcounting.Lack of server-side validationUnlike your ERP, we don’t verify payment success or customer info. If someone abandons the cart but still loads the confirmation page, we’ll count the conversion.

Duplicate pixel firesIf a user refreshes the thank-you page, the pixel may fire again. This will count as a second conversion.

Duplicate pixel fires

If a user refreshes the thank-you page, the pixel may fire again. This will count as a second conversion.

Multiple user visits to confirmation pagesIf users revisit the confirmation URL (via email links, bookmarks, or back button), the pixel fires again.

Multiple user visits to confirmation pages

If users revisit the confirmation URL (via email links, bookmarks, or back button), the pixel fires again.

Pixel placed on the wrong URL(s)If the pixel is notexclusivelyon the final “thank you” page, it might be firing on other pages as well, leading to overcounting.

Pixel placed on the wrong URL(s)

If the pixel is notexclusivelyon the final “thank you” page, it might be firing on other pages as well, leading to overcounting.

Lack of server-side validationUnlike your ERP, we don’t verify payment success or customer info. If someone abandons the cart but still loads the confirmation page, we’ll count the conversion.

Lack of server-side validation

Unlike your ERP, we don’t verify payment success or customer info. If someone abandons the cart but still loads the confirmation page, we’ll count the conversion.



How to fix it:

Make sure the pixel is placedonlyon a unique, non-cacheable “thank you” page.Use server-side conditions (e.g., only firing the pixel if the order is confirmed).Consider firing the pixel only once per session using logic on your side.

Make sure the pixel is placedonlyon a unique, non-cacheable “thank you” page.

Make sure the pixel is placedonlyon a unique, non-cacheable “thank you” page.

Use server-side conditions (e.g., only firing the pixel if the order is confirmed).

Use server-side conditions (e.g., only firing the pixel if the order is confirmed).

Consider firing the pixel only once per session using logic on your side.

Consider firing the pixel only once per session using logic on your side.



Sealmetrics will always showexactly what is triggered, nothing more, nothing less. If the ERP shows fewer conversions or revenue, it’s likely becausethe pixel is firing more often than it should.

[How SuperPrivacy Tracking Works](https://help.sealmetrics.com/en/articles/9667399-how-superprivacy-tracking-works)[Why Does GA4 Measure More Than Sealmetrics?](https://help.sealmetrics.com/en/articles/10006652-why-does-ga4-measure-more-than-sealmetrics)[Setting Up Trackers in Sealmetrics](https://help.sealmetrics.com/en/articles/10054456-setting-up-trackers-in-sealmetrics)[How to Measure Conversions and Micro-Conversions](https://help.sealmetrics.com/en/articles/10208596-how-to-measure-conversions-and-micro-conversions)[SealMetrics Kick off [Video]](https://help.sealmetrics.com/en/articles/10364275-sealmetrics-kick-off-video)[SealMetrics Help Center](/en/)Company

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