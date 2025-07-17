---
title: Why Does GA4 Measure More Than Sealmetrics?
description: ''
slug: why-does-ga4-measure-more-than-sealmetrics?
---
[Skip to main content](#main-content)![Image](why-does-ga4-measure-more-than-sealmetrics?/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Metric Insights](https://help.sealmetrics.com/en/collections/10013737-metric-insights)If GA4 shows more data than Sealmetrics, it's likely due to implementation issues. In other words, GA4 could be tracking without consent, or the Sealmetrics pixel may be blocked by Google Tag Manager (GTM) or the cookie banner. Below are the steps to investigate this issue.



Steps to Follow:

Check if the Cookie Banner is Blocking Cookies Before ConsentOften, GA4 cookies are not blocked by the cookie banner. This means GA4 is tracking 100% of the traffic, which violates privacy regulations. You can check which cookies are added to your site without user consent using our freeCookie Scannertool. If GA4 is measuring more traffic than it should, this is likely the cause.Ensure the Cookie Banner is Not Blocking the Sealmetrics PixelCookie banners typically block the JavaScript that generates the cookies, not the cookies themselves. Incorrect implementation may cause the cookie banner to block Sealmetrics' JavaScript, resulting in Sealmetrics tracking less traffic, as it only measures data when the user gives consent.Verify That Consent Mode v2 is Implemented CorrectlySometimes, Consent Mode v2 is set up in a way that web analytics cookies are accepted by default, causing GA4 to fire cookies without user consent. You can verify this with ourConsent Mode Checkertool. If the result is blank, your Consent Mode might not be set up properly, or you're using the Basic version instead of Advanced.Review Your Google Tag Manager ConfigurationIf the cookie banner operates through rules set in GTM, it might be that Sealmetrics' pixel only triggers after user consent. Make sure GTM is configured so that Sealmetrics can accurately measure traffic.

Check if the Cookie Banner is Blocking Cookies Before ConsentOften, GA4 cookies are not blocked by the cookie banner. This means GA4 is tracking 100% of the traffic, which violates privacy regulations. You can check which cookies are added to your site without user consent using our freeCookie Scannertool. If GA4 is measuring more traffic than it should, this is likely the cause.

Check if the Cookie Banner is Blocking Cookies Before ConsentOften, GA4 cookies are not blocked by the cookie banner. This means GA4 is tracking 100% of the traffic, which violates privacy regulations. You can check which cookies are added to your site without user consent using our freeCookie Scannertool. If GA4 is measuring more traffic than it should, this is likely the cause.

[Cookie Scanner](https://sealmetrics.com/free-cookie-scanner/)Ensure the Cookie Banner is Not Blocking the Sealmetrics PixelCookie banners typically block the JavaScript that generates the cookies, not the cookies themselves. Incorrect implementation may cause the cookie banner to block Sealmetrics' JavaScript, resulting in Sealmetrics tracking less traffic, as it only measures data when the user gives consent.

Ensure the Cookie Banner is Not Blocking the Sealmetrics PixelCookie banners typically block the JavaScript that generates the cookies, not the cookies themselves. Incorrect implementation may cause the cookie banner to block Sealmetrics' JavaScript, resulting in Sealmetrics tracking less traffic, as it only measures data when the user gives consent.

Verify That Consent Mode v2 is Implemented CorrectlySometimes, Consent Mode v2 is set up in a way that web analytics cookies are accepted by default, causing GA4 to fire cookies without user consent. You can verify this with ourConsent Mode Checkertool. If the result is blank, your Consent Mode might not be set up properly, or you're using the Basic version instead of Advanced.

Verify That Consent Mode v2 is Implemented CorrectlySometimes, Consent Mode v2 is set up in a way that web analytics cookies are accepted by default, causing GA4 to fire cookies without user consent. You can verify this with ourConsent Mode Checkertool. If the result is blank, your Consent Mode might not be set up properly, or you're using the Basic version instead of Advanced.

[Consent Mode Checker](https://sealmetrics.com/consent-mode-checker/)Review Your Google Tag Manager ConfigurationIf the cookie banner operates through rules set in GTM, it might be that Sealmetrics' pixel only triggers after user consent. Make sure GTM is configured so that Sealmetrics can accurately measure traffic.

Review Your Google Tag Manager ConfigurationIf the cookie banner operates through rules set in GTM, it might be that Sealmetrics' pixel only triggers after user consent. Make sure GTM is configured so that Sealmetrics can accurately measure traffic.

Following these steps can help ensure accurate measurement and compliance with privacy regulations.

[Setting Up Trackers in Sealmetrics](https://help.sealmetrics.com/en/articles/10054456-setting-up-trackers-in-sealmetrics)[Why We Can’t Filter Internal Traffic at SealMetrics](https://help.sealmetrics.com/en/articles/10111689-why-we-can-t-filter-internal-traffic-at-sealmetrics)[SealMetrics Kick off [Video]](https://help.sealmetrics.com/en/articles/10364275-sealmetrics-kick-off-video)[What attribution model does Sealmetrics use?](https://help.sealmetrics.com/en/articles/11461584-what-attribution-model-does-sealmetrics-use)[What is gtm-msr.appspot.com?](https://help.sealmetrics.com/en/articles/11721807-what-is-gtm-msr-appspot-com)[SealMetrics Help Center](/en/)Company

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