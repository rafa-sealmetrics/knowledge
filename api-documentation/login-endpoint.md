---
title: Login Endpoint
description: ''
slug: login-endpoint
---
[Skip to main content](#main-content)![Image](login-endpoint/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



The Login endpoint authenticates users and provides an access token that must be used for all subsequent API requests.



Endpoint Details



-URL: `https://app.sealmetrics.com/api/auth/login`

[https://app.sealmetrics.com/api/auth/login`](https://app.sealmetrics.com/api/auth/login`)-Method: POST

-Content-Type: application/json



Request Parameters



Headers

Header

Value

Required

Content-Type

application/json

Yes



Body Parameters



Parameter

Type

Required

Description

email

string

Yes

Your registered email address

password

string

Yes

Your account password



Example Request



cURL



```bash

curl --location 'https://app.sealmetrics.com/api/auth/login' \

[https://app.sealmetrics.com/api/auth/login](https://app.sealmetrics.com/api/auth/login)--header 'Content-Type: application/json' \

--data-raw '{

"email": "[email protected]",

[[email protected]](/cdn-cgi/l/email-protection#bedadbd3d1fecddbdfd2d3dbcaccd7ddcd90ddd1d3)"password": "demo"

}'

```



Python



```python

import requests

import json



url = "https://app.sealmetrics.com/api/auth/login"

[https://app.sealmetrics.com/api/auth/login](https://app.sealmetrics.com/api/auth/login)

payload = json.dumps({

"email": "[email protected]",

[[email protected]](/cdn-cgi/l/email-protection#0e6a6b63614e7d6b6f62636b7a7c676d7d206d6163)"password": "demo"

})

headers = {

'Content-Type': 'application/json'

}



response = requests.request("POST", url, headers=headers, data=payload)



print(response.text)

```



JavaScript



```javascript

var myHeaders = new Headers();

myHeaders.append("Content-Type", "application/json");



var raw = JSON.stringify({

"email": "[email protected]",

[[email protected]](/cdn-cgi/l/email-protection#4327262e2c033026222f2e2637312a20306d202c2e)"password": "demo"

});



var requestOptions = {

method: 'POST',

headers: myHeaders,

body: raw,

redirect: 'follow'

};



fetch("https://app.sealmetrics.com/api/auth/login", requestOptions)

[https://app.sealmetrics.com/api/auth/login](https://app.sealmetrics.com/api/auth/login).then(response => response.text())

.then(result => console.log(result))

.catch(error => console.log('error', error));

```



Response



Success Response (200 OK)



```json

{

"access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI6ImpoaS1Nzg5MzQzIn0...",

"token_type": "Bearer",

"expires_at": "2025-07-09T18:14:44.000000Z"

}

```



Response Parameters



Parameter

Type

Description

access_token

string

JWT token to be used for authentication in subsequent requests

token_type

string

Type of token (always "Bearer")

expires_at

string

ISO 8601 timestamp indicating when the token will expire



Error Response (401 Unauthorized)



```json

{

"status": "error",

"message": "Invalid credentials"

}

```



Notes



- The access token has an expiration time, after which you'll need to request a new token

- Store the token securely and include it in all subsequent API requests

- Do not share your credentials or token with unauthorized parties



[Authentication](https://help.sealmetrics.com/en/articles/11124953-authentication)[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Account Endpoints](https://help.sealmetrics.com/en/articles/11125188-account-endpoints)[Conversions Endpoint](https://help.sealmetrics.com/en/articles/11125264-conversions-endpoint)[Set-Click Endpoint](https://help.sealmetrics.com/en/articles/11125384-set-click-endpoint)[SealMetrics Help Center](/en/)Company

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