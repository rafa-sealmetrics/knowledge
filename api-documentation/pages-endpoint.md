---
title: Pages Endpoint
description: ''
slug: pages-endpoint
---
[Skip to main content](#main-content)![Image](pages-endpoint/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



The Pages endpoint provides detailed analytics about page views and traffic to your website pages. This endpoint allows you to retrieve metrics such as views, entry pages, and other page-related statistics.



Endpoint Details



-URL: `https://app.sealmetrics.com/api/report/pages`

[https://app.sealmetrics.com/api/report/pages`](https://app.sealmetrics.com/api/report/pages`)-Method: GET

-Authentication: Bearer Token required



Request Parameters

Headers

Header

Value

Required

Authorization

Bearer {your_access_token}

Yes

Authorization

application/json

Yes

Connection

keep-alive

Recommended

Accept-Encoding

gzip, deflate, br

Recommended



Query Parameters

Parameter

Type

Required

Description

account_id

string

Yes

Your account identifier

date_range

string

Yes

Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`)

skip

integer

No

Number of records to skip (for pagination), defaults to 0

limit

integer

No

Maximum number of records to return, defaults to 100 with max value of 100

country

string

No

ISO 3166-1 alpha-2 country code filter

utm_medium

string

No

Filter by medium (e.g., email, cpc, social media)

utm_source

string

No

Filter by source (e.g., google, facebook, newsletter)

show_utms

boolean

No

Flag to display UTM parameters (default: false)



Example Request



cURL



```bash

curl --location 'https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100' \

[https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100](https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100)--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \

--header 'Accept: application/json' \

--header 'Connection: keep-alive' \

--header 'Accept-Encoding: gzip, deflate, br'

```



Python



```python

import requests



url = "https://app.sealmetrics.com/api/report/pages"

[https://app.sealmetrics.com/api/report/pages](https://app.sealmetrics.com/api/report/pages)

querystring = {

"account_id": "000000000000000000001234",

"date_range": "this_month",

"skip": "0",

"limit": "100"

}



headers = {

"Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...",

"Accept": "application/json",

"Connection": "keep-alive",

"Accept-Encoding": "gzip, deflate, br"

}



response = requests.request("GET", url, headers=headers, params=querystring)



print(response.text)

```



JavaScript



```javascript

var myHeaders = new Headers();

myHeaders.append("Authorization", "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...");

myHeaders.append("Accept", "application/json");

myHeaders.append("Connection", "keep-alive");

myHeaders.append("Accept-Encoding", "gzip, deflate, br");



var requestOptions = {

method: 'GET',

headers: myHeaders,

redirect: 'follow'

};



fetch("https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100", requestOptions)

[https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100](https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100).then(response => response.text())

.then(result => console.log(result))

.catch(error => console.log('error', error));

```



Response



Success Response (200 OK)



```json

{

"status": "ok",

"data": [

{

"url": "/",

"views": 21955,

"entry_page": 7221

},

{

"url": "/agencia-seo",

"views": 8765,

"entry_page": 3421

},

{

"url": "/blog/marketing-digital",

"views": 5432,

"entry_page": 2198

}

// Additional results...

]

}

```



Response Parameters



The response data array contains objects with the following fields:

Field

Type

Description

url

string

The page URL path

views

number

Total number of page views

entry_page

number

Number of sessions where this was the first page visited



| Field | Type | Description |

|-------|------|-------------|

| url | string | The page URL path |

| views | number | Total number of page views |

| entry_page | number | Number of sessions where this was the first page visited |



Error Response (401 Unauthorized)



```json

{

"status": "error",

"message": "Unauthenticated"

}

```



### Error Response (400 Bad Request)



```json

{

"status": "error",

"message": "Missing required parameter: account_id"

}

```



Notes



- Results are typically ordered by page views in descending order

- Use the `utm_` parameters to filter pages by specific marketing campaigns

- The `show_utms` parameter can be set to `true` to include UTM parameter details in the response

- Use pagination parameters (`skip` and `limit`) for websites with many pages



[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Account Endpoints](https://help.sealmetrics.com/en/articles/11125188-account-endpoints)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[Microconversions Endpoint](https://help.sealmetrics.com/en/articles/11125290-microconversions-endpoint)[ROAs Evolution Endpoint](https://help.sealmetrics.com/en/articles/11125318-roas-evolution-endpoint)[SealMetrics Help Center](/en/)Company

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