---
title: Funnel Endpoint
description: ''
slug: funnel-endpoint
---
[Skip to main content](#main-content)![Image](funnel-endpoint/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



The Funnel endpoint provides detailed analytics about your sales or conversion funnel, showing how users progress through different customer journey stages. This endpoint allows you to analyze conversion rates between stages and identify potential bottlenecks in your funnel.



Endpoint Details



-URL: `https://app.sealmetrics.com/api/report/funnel`

[https://app.sealmetrics.com/api/report/funnel`](https://app.sealmetrics.com/api/report/funnel`)-Method: GET

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

report_type

string

Yes

Type of report to generate (typically "Source")

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

ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)



Example Request



cURL



```bash

curl --location 'https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100' \

[https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100](https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100)--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \

--header 'Accept: application/json' \

--header 'Connection: keep-alive' \

--header 'Accept-Encoding: gzip, deflate, br'

```



Python



```python

import requests



url = "https://app.sealmetrics.com/api/report/funnel"

[https://app.sealmetrics.com/api/report/funnel](https://app.sealmetrics.com/api/report/funnel)

querystring = {

"account_id": "000000000000000000001234",

"report_type": "Source",

"date_range": "20230601,20230630",

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



fetch("https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100", requestOptions)

[https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100](https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100).then(response => response.text())

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

"Source": "Referrer",

"clicks": 9380,

"conversions": 675,

"microconversions": 2843,

"add-to-cart": 571,

"checkout": 587

},

{

"Source": "Google",

"clicks": 12450,

"conversions": 892,

"microconversions": 3256,

"add-to-cart": 743,

"checkout": 812

},

{

"Source": "Facebook",

"clicks": 8765,

"conversions": 523,

"microconversions": 1987,

"add-to-cart": 412,

"checkout": 398

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

Source

string

The source name (or other grouping based on report_type)

clicks

number

Number of clicks from this source

conversions

number

Number of final conversions from this source

microconversions

number

Number of microconversions from this source

add-to-cart

number

Number of add-to-cart actions from this source

checkout

number

Number of checkout initiations from this source

*Additional funnel stages*

number

Other funnel stages may appear depending on your configuration



Error Response (401 Unauthorized)



```json

{

"status": "error",

"message": "Unauthenticated"

}

```



Error Response (400 Bad Request)



```json

{

"status": "error",

"message": "Missing required parameter: account_id"

}

```



Notes



- The funnel endpoint provides a comprehensive view of how users move through your conversion process

- The specific funnel stages shown in the response will depend on your account configuration

- Use this data to identify where users are dropping off in your conversion process

- Compare funnel performance across different traffic sources to optimize marketing efforts

- The `report_type` parameter determines how the data is grouped (e.g., by Source, Medium, Campaign)



[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Pages Endpoint](https://help.sealmetrics.com/en/articles/11125236-pages-endpoint)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[Microconversions Endpoint](https://help.sealmetrics.com/en/articles/11125290-microconversions-endpoint)[ROAs Evolution Endpoint](https://help.sealmetrics.com/en/articles/11125318-roas-evolution-endpoint)[SealMetrics Help Center](/en/)Company

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