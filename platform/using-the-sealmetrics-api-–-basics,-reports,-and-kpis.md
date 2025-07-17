---
title: "Using the SealMetrics API \u2013 Basics, Reports, and KPIs"
description: ''
slug: "using-the-sealmetrics-api-\u2013-basics,-reports,-and-kpis"
---
[Skip to main content](#main-content)![Image](using-the-sealmetrics-api-–-basics,-reports,-and-kpis/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Platform](https://help.sealmetrics.com/en/collections/10013736-platform)Overview of the SealMetrics API

The SealMetrics API is a powerful tool for programmatically accessing data, reports, and KPIs from your analytics platform. This guide covers the essential information needed to start using the API effectively and includes examples to help you better understand it.



Getting Started with the API

API Endpoint: Please make sure you have access to the base URL for API calls.Authentication: The API uses token-based authentication. Include your API key in the header for secure access.Example Code (cURL):bashCopy codecurl -X GET "https://api.sealmetrics.com/v1/reports" \ -H "Authorization: Bearer YOUR_API_KEY"

API Endpoint: Please make sure you have access to the base URL for API calls.

API Endpoint: Please make sure you have access to the base URL for API calls.

Authentication: The API uses token-based authentication. Include your API key in the header for secure access.Example Code (cURL):bashCopy codecurl -X GET "https://api.sealmetrics.com/v1/reports" \ -H "Authorization: Bearer YOUR_API_KEY"

Authentication: The API uses token-based authentication. Include your API key in the header for secure access.

Example Code (cURL):





Accessing Reports

The API provides access to various reports, including traffic analytics, user behavior, and performance metrics. You can request data such as:

Daily Traffic Reports: Obtain metrics on page views, unique visitors, and session duration.Event Tracking Reports: Access data on custom user interactions for in-depth analysis.

Daily Traffic Reports: Obtain metrics on page views, unique visitors, and session duration.

Daily Traffic Reports: Obtain metrics on page views, unique visitors, and session duration.

Event Tracking Reports: Access data on custom user interactions for in-depth analysis.

Event Tracking Reports: Access data on custom user interactions for in-depth analysis.



Example Request for a Report:





KPIs Available Through the API

SealMetrics allows you to track several key performance indicators (KPIs) for more insightful analysis:

Page Views: Total number of pages viewed by users.Unique Visitors: Count of distinct visitors during a specified time period.Session Duration: Average time spent by users on your website.Conversion Rates: Percentage of users who complete desired actions on your site.

Page Views: Total number of pages viewed by users.

Page Views: Total number of pages viewed by users.

Unique Visitors: Count of distinct visitors during a specified time period.

Unique Visitors: Count of distinct visitors during a specified time period.

Session Duration: Average time spent by users on your website.

Session Duration: Average time spent by users on your website.

Conversion Rates: Percentage of users who complete desired actions on your site.

Conversion Rates: Percentage of users who complete desired actions on your site.

Example JSON Response:





Best Practices for Using the API

Rate Limiting: Be aware of any rate limits to prevent throttling.Data Handling: Use secure storage for API keys and implement error handling in your applications.Filtering Data: Apply filters to tailor your report data to specific periods, user segments, or events.

Rate Limiting: Be aware of any rate limits to prevent throttling.

Rate Limiting: Be aware of any rate limits to prevent throttling.

Data Handling: Use secure storage for API keys and implement error handling in your applications.

Data Handling: Use secure storage for API keys and implement error handling in your applications.

Filtering Data: Apply filters to tailor your report data to specific periods, user segments, or events.

Filtering Data: Apply filters to tailor your report data to specific periods, user segments, or events.





Conclusion

With these tools and tips, you can effectively harness the SealMetrics API to integrate analytics into your workflows, providing greater data management and insights flexibility.

For more detailed API documentation, refer to theSealMetrics API Documentation.

[SealMetrics API Documentation](https://documenter.getpostman.com/view/485655/TzRVdkVu)[Why Does GA4 Measure More Than Sealmetrics?](https://help.sealmetrics.com/en/articles/10006652-why-does-ga4-measure-more-than-sealmetrics)[How SealMetrics Blocks Bot Traffic Without Handling IPs](https://help.sealmetrics.com/en/articles/10111680-how-sealmetrics-blocks-bot-traffic-without-handling-ips)[Bot Traffic Filtering in Sealmetrics](https://help.sealmetrics.com/en/articles/10506133-bot-traffic-filtering-in-sealmetrics)[How Sealmetrics Tracks Traffic Without Cookies](https://help.sealmetrics.com/en/articles/11125666-how-sealmetrics-tracks-traffic-without-cookies)[How Sealmetrics Consolidates Data](https://help.sealmetrics.com/en/articles/11680335-how-sealmetrics-consolidates-data)[SealMetrics Help Center](/en/)Company

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