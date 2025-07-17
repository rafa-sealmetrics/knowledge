---
title: Authentication
description: ''
slug: authentication
---
[Skip to main content](#main-content)![Image](authentication/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Overview



API Seal Metrics uses Bearer token authentication to secure all API requests. Before you can access any data endpoints, you must obtain an authentication token through the login process. This token must be included in the Authorization header of all subsequent API requests.



Login Endpoint



To authenticate with the API and obtain a token, you need to make a POST request to the login endpoint.



Endpoint: `https://app.sealmetrics.com/api/auth/login`

[https://app.sealmetrics.com/api/auth/login`](https://app.sealmetrics.com/api/auth/login`)

Request Headers

Header

Value

Content-Type

application/json



Request Body



The login request requires your email and password in JSON format:



```json

{

"email": "[email protected]",

[[email protected]](/cdn-cgi/l/email-protection#047d6b71765b6169656d6844617c65697468612a676b69)"password": "your_password"

}

```



Example Request (cURL)



```bash

curl --location 'https://app.sealmetrics.com/api/auth/login' \

[https://app.sealmetrics.com/api/auth/login](https://app.sealmetrics.com/api/auth/login)--header 'Content-Type: application/json' \

--data-raw '{

"email": "[email protected]",

[[email protected]](/cdn-cgi/l/email-protection#fd99989092bd8e989c919098898f949e8ed39e9290)"password": "demo"

}'

```



Response



Upon successful authentication, the server will respond with a JSON object containing your access token, token type, and expiration information:



```json

{

"access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI6ImpoaS1Nzg5MzQzIn0...",

"token_type": "Bearer",

"expires_at": "2025-07-09T18:14:44.000000Z"

}

```



Using the Token



For all subsequent API requests, you must include the obtained token in the Authorization header using the Bearer scheme:



Required Headers for Authenticated Requests

Header

Value

Authorization

Bearer {your_access_token}

Accept

application/json

Connection

keep-alive

Accept-Encoding

gzip, deflate, br



Example Authenticated Request (cURL)

curl --location 'https://app.sealmetrics.com/api/report/acquisition?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100' \

[https://app.sealmetrics.com/api/report/acquisition?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100](https://app.sealmetrics.com/api/report/acquisition?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100)--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \

--header 'Accept: application/json' \

--header 'Connection: keep-alive' \

--header 'Accept-Encoding: gzip, deflate, br'



Token Expiration and Renewal



The authentication token has an expiration time, which is included in the `expires_at` field of the login response. To maintain uninterrupted access to the API, you should:



1. Store the expiration time along with the token

2. Check the token's validity before making API requests

3. If the token is expired or about to expire, request a new token using the login endpoint

4. Update your stored token with the new one



Security Best Practices



To ensure the security of your API access:



1.Never hardcode credentialsin your application code

2. Store API credentials securely using environment variables or a secure credential manager

3. Implement proper error handling for authentication failures

4. Set up automatic token renewal before expiration

5. Use HTTPS for all API communications

6. Limit access to your authentication token within your application

7. Implement proper logging for authentication events for audit purposes



Troubleshooting Authentication Issues



If you encounter authentication problems:



1.401 Unauthorized: Verify that you're using the correct email and password

2.Token Expired: Check if your token has expired and request a new one

3.Invalid Token Format: Ensure you're correctly formatting the Authorization header

4.Connection Issues: Verify your network connection and the API service status



If problems persist, please contact API Seal Metrics support with details about the specific error messages you're getting.



[Login Endpoint](https://help.sealmetrics.com/en/articles/11124976-login-endpoint)[Acquisition Endpoint](https://help.sealmetrics.com/en/articles/11125053-acquisition-endpoint)[Account Endpoints](https://help.sealmetrics.com/en/articles/11125188-account-endpoints)[Troubleshooting](https://help.sealmetrics.com/en/articles/11125518-troubleshooting)[Implementation Guides](https://help.sealmetrics.com/en/articles/11125557-implementation-guides)[SealMetrics Help Center](/en/)Company

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