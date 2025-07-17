---
title: "How to Avoid Conversions Being Attributed to \u201CPayment\u201D in Sealmetrics"
description: ''
slug: "how-to-avoid-conversions-being-attributed-to-\u201Cpayment\u201D-in-sealmetrics"
---
[Skip to main content](#main-content)![Image](how-to-avoid-conversions-being-attributed-to-“payment”-in-sealmetrics/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Platform](https://help.sealmetrics.com/en/collections/10013736-platform)When users complete a purchase on your website and are redirected to apayment gateway(like Stripe, PayPal, Redsys, etc.), they temporarily leave your site. When they return to yourthank you page, Sealmetrics detects this as a new session.

If the payment gateway domain is not on our predefined list, the session is attributed to asource = payment.



This means:

✅ The conversion is tracked

❌ But the original source (Google Ads, Facebook, Email, etc.) is lost



That’s a problem if you care about real attribution — and we assume you do.





Why Sealmetrics Attributes “Payment” as a Source



Sealmetrics is privacy-first and doesn’t rely on cookies or fingerprinting.

Instead, we identify sessions based on signals like browser, OS, screen size, and timestamps.



So when the user leaves your site and comes back from a third-party domain (like secure.paymentsite.com), it’s treated as anew session, unless:



The domain is on ourknown list of payment providersOr you implement areferrer bypass system

The domain is on ourknown list of payment providers

The domain is on ourknown list of payment providers

Or you implement areferrer bypass system

Or you implement areferrer bypass system



When Does This Happen?



You’ll typically see conversions from “source = payment” when:

The payment provider uses a redirect flowThe return to the thank you page creates a new sessionThe referrer is the payment provider, not the original traffic source

The payment provider uses a redirect flow

The payment provider uses a redirect flow

The return to the thank you page creates a new session

The return to the thank you page creates a new session

The referrer is the payment provider, not the original traffic source

The referrer is the payment provider, not the original traffic source

Example:

A user clicks on a Google Ads campaignThey add items to cart → proceed to checkoutThey pay via payments.xyz.comThey’re redirected to /thank-you→ Sealmetrics detects referrer = payments.xyz.com→ Source is recorded as payment instead of Google Ads

A user clicks on a Google Ads campaign

A user clicks on a Google Ads campaign

They add items to cart → proceed to checkout

They add items to cart → proceed to checkout

They pay via payments.xyz.com

They pay via payments.xyz.com

They’re redirected to /thank-you→ Sealmetrics detects referrer = payments.xyz.com→ Source is recorded as payment instead of Google Ads

They’re redirected to /thank-you

→ Sealmetrics detects referrer = payments.xyz.com

→ Source is recorded as payment instead of Google Ads

How to fix it:

![Image](how-to-avoid-conversions-being-attributed-to-“payment”-in-sealmetrics/Seal-Metrics-04-25-2025_04_15_PM28129.png)





![Image](how-to-avoid-conversions-being-attributed-to-“payment”-in-sealmetrics/Seal-Metrics-04-25-2025_04_16_PM28129.png)



Instead of adding "consentmode.sealmetrics.net"add the Payment Gateway Domain.

[SealMetrics Kick off [Video]](https://help.sealmetrics.com/en/articles/10364275-sealmetrics-kick-off-video)[How Sealmetrics Tracks Traffic Without Cookies](https://help.sealmetrics.com/en/articles/11125666-how-sealmetrics-tracks-traffic-without-cookies)[Understanding Referrer Loss and Direct Traffic in Sealmetrics](https://help.sealmetrics.com/en/articles/11125734-understanding-referrer-loss-and-direct-traffic-in-sealmetrics)[How SealMetrics Calculates SEO Traffic](https://help.sealmetrics.com/en/articles/11154410-how-sealmetrics-calculates-seo-traffic)[What attribution model does Sealmetrics use?](https://help.sealmetrics.com/en/articles/11461584-what-attribution-model-does-sealmetrics-use)[SealMetrics Help Center](/en/)Company

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