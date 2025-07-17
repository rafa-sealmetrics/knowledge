---
title: API Endpoints
description: ''
slug: api-endpoints
---
[Skip to main content](#main-content)![Image](api-endpoints/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)

This section provides detailed documentation for each endpoint available in the API Seal Metrics v1.0, including required parameters, optional parameters, example requests, and example responses.



Common Parameters



Before diving into specific endpoints, let's review the common parameters used across multiple endpoints:



Parameter

Type

Description

account_id

string

Your account identifier (required for most endpoints)

date_range

string

Date range for the data in format YYYYMMDD,YYYYMMDD or predefined values

skip

integer

Number of records to skip (for pagination), defaults to 0

limit

integer

Maximum number of records to return, defaults to 100 with max value of 100

country

string

ISO 3166-1 alpha-2 country code filter (optional)

utm_medium

string

Filter by medium (e.g., email, cpc, social media)

utm_source

string

Filter by source (e.g., google, facebook, newsletter)

utm_campaign

string

Filter by campaign name

show_utms

boolean

Flag to display UTM parameters (default: false)



Date Range Options



The `date_range` parameter accepts the following formats:

- Specific date range: `20230601,20230630` (YYYYMMDD,YYYYMMDD)

- Predefined periods:

- `today`

- `yesterday`

- `last_7_days`

- `last_14_days`

- `last_30_days`

- `last_60_days`

- `last_90_days`

- `this_month`

- `last_month`

- `this_week_monday_sunday`

- `this_week_sunday_saturday`

- `this_year`

- `last_year`



[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Pages Endpoint](https://help.sealmetrics.com/en/articles/11125236-pages-endpoint)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[ROAs Evolution Endpoint](https://help.sealmetrics.com/en/articles/11125318-roas-evolution-endpoint)[Funnel Endpoint](https://help.sealmetrics.com/en/articles/11125349-funnel-endpoint)[SealMetrics Help Center](/en/)Company

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