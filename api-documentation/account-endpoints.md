---
title: Account Endpoints
description: ''
slug: account-endpoints
---
[Skip to main content](#main-content)![Image](account-endpoints/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



The Accounts endpoint provides information about the accounts associated with your API credentials. This endpoint allows you to retrieve account details that can be used in other API requests.



Endpoint Details



-URL: `https://app.sealmetrics.com/api/auth/accounts`

[https://app.sealmetrics.com/api/auth/accounts`](https://app.sealmetrics.com/api/auth/accounts`)-Method: GET

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



This endpoint does not require any query parameters.



Example Request

cURL



```bash

curl --location 'https://app.sealmetrics.com/api/auth/accounts' \

[https://app.sealmetrics.com/api/auth/accounts](https://app.sealmetrics.com/api/auth/accounts)--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \

--header 'Accept: application/json' \

--header 'Connection: keep-alive' \

--header 'Accept-Encoding: gzip, deflate, br'

```



Python



```python

import requests



url = "https://app.sealmetrics.com/api/auth/accounts"

[https://app.sealmetrics.com/api/auth/accounts](https://app.sealmetrics.com/api/auth/accounts)

headers = {

"Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...",

"Accept": "application/json",

"Connection": "keep-alive",

"Accept-Encoding": "gzip, deflate, br"

}



response = requests.request("GET", url, headers=headers)



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



fetch("https://app.sealmetrics.com/api/auth/accounts", requestOptions)

[https://app.sealmetrics.com/api/auth/accounts](https://app.sealmetrics.com/api/auth/accounts).then(response => response.text())

.then(result => console.log(result))

.catch(error => console.log('error', error));

```



Response



Success Response (200 OK)



```json

{

"status": "ok",

"data": {

"000000000000000000001234": "Demo Account"

}

}

```



Response Parameters



The response data object contains key-value pairs where:

- Key: Account ID (string)

- Value: Account name (string)



Error Response (401 Unauthorized)



```json

{

"status": "error",

"message": "Unauthenticated"

}

```



Notes



- This endpoint is helpful in retrieving the account IDs needed for other API requests

- The account IDs returned by this endpoint should be used in the `account_id` parameter for other endpoints

- If you have access to multiple accounts, all of them will be returned in the response



[Authentication](https://help.sealmetrics.com/en/articles/11124953-authentication)[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Pages Endpoint](https://help.sealmetrics.com/en/articles/11125236-pages-endpoint)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[Funnel Endpoint](https://help.sealmetrics.com/en/articles/11125349-funnel-endpoint)[SealMetrics Help Center](/en/)Company

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