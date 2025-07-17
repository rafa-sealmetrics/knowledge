---
title: ROAs Evolution Endpoint
description: ''
slug: roas-evolution-endpoint
---
[Skip to main content](#main-content)![Image](roas-evolution-endpoint/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



The ROAS Evolution endpoint provides detailed analytics about Return on Advertising Spend (ROAS) over time. This endpoint allows you to track and analyze the effectiveness of your marketing investments across different channels and campaigns.





Endpoint Details



-URL: `https://app.sealmetrics.com/api/report/roas-evolution`

[https://app.sealmetrics.com/api/report/roas-evolution`](https://app.sealmetrics.com/api/report/roas-evolution`)-Method: GET

-Authentication: Bearer Token required



Request Parameters

Headers

Header

Value

Required

Authorization

Bearer {your_access_token}

Yes

Accept

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

time_unit

string

No

Time unit for data aggregation: "daily", "weekly", or "monthly" (default: "daily")

utm_medium

string

No

Filter by medium (e.g., seo, cpc)

utm_source

string

No

Filter by source (e.g., google, newsletter)

utm_campaign

string

No

Filter by campaign name

country

string

No

ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain



Example Request



cURL



```bash

curl --location 'https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily' \

[https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily](https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily)--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \

--header 'Accept: application/json' \

--header 'Connection: keep-alive' \

--header 'Accept-Encoding: gzip, deflate, br'

```



Python



```python

import requests



url = "https://app.sealmetrics.com/api/report/roas-evolution"

[https://app.sealmetrics.com/api/report/roas-evolution](https://app.sealmetrics.com/api/report/roas-evolution)

querystring = {

"account_id": "000000000000000000001234",

"date_range": "this_month",

"skip": "0",

"limit": "100",

"time_unit": "daily"

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



fetch("https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily", requestOptions)

[https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily](https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily).then(response => response.text())

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

"_id": "2024-07-01",

"clicks": 1623,

"page_views": 10458,

"conversions": 117,

"microconversions": 441,

"revenue": 42466.97

},

{

"_id": "2024-07-02",

"clicks": 1845,

"page_views": 11258,

"conversions": 132,

"microconversions": 487,

"revenue": 38975.23

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

_id

string

Date or time period identifier (format depends on time_unit parameter)

clicks

number

Number of clicks during the time period

page_views

number

Number of page views during the time period

conversions

number

Number of conversions during the time period

microconversions

number

Number of microconversions during the time period

revenue

number

Total revenue generated during the time period



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



- The `time_unit` parameter determines how data is aggregated in the response

- Use "daily" for detailed day-by-day analysis, "weekly" for week-over-week trends, or "monthly" for broader patterns

- This endpoint is particularly useful for visualizing performance trends over time

- Combine with UTM filters to analyze specific marketing channels or campaigns

- The data can be used to calculate ROAS by dividing revenue by advertising spend for each time period



[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Pages Endpoint](https://help.sealmetrics.com/en/articles/11125236-pages-endpoint)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[Microconversions Endpoint](https://help.sealmetrics.com/en/articles/11125290-microconversions-endpoint)[Funnel Endpoint](https://help.sealmetrics.com/en/articles/11125349-funnel-endpoint)[SealMetrics Help Center](/en/)Company

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