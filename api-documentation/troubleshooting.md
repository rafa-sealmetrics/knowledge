---
title: Troubleshooting
description: ''
slug: troubleshooting
---
[Skip to main content](#main-content)![Image](troubleshooting/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[API Documentation](https://help.sealmetrics.com/en/collections/12580132-api-documentation)Common Errors

- 401 Unauthorized: This typically means your authentication token is invalid or has expired.

- Solution: Request a new token using the login endpoint.



- "Invalid credentials": This means the email or password provided to the login endpoint is incorrect.

- Solution: Verify your credentials and try again.



- 400 Bad Request: This usually means there's an issue with your request parameters.

-Solution: Check the error message for details about which parameter is missing or invalid.



- 404 Not Found: This means the endpoint URL is incorrect.

- Solution: Verify the endpoint URL and ensure it matches the documentation.



- 429 Too Many Requests: This means you've exceeded the rate limit for API requests.

- Solution: Implement exponential backoff and retry logic in your code.





- JSON Decode Error: This occurs when trying to parse a non-JSON response.

- Solution: Check if the API returned an error message or if the endpoint doesn't return JSON.



Debugging Tips



1. Enable Verbose Logging: Set up detailed logging for API requests and responses to help identify issues.



2. Check Request Headers: Please make sure all required headers are included in your requests.



3. Validate Parameters: Verify that all required parameters are included and formatted correctly.



4. Test with cURL: Use cURL commands to test API endpoints directly before implementing in your code.



5. Check Token Expiration: Ensure your authentication token hasn't expired before making requests.



Support Resources



If you encounter persistent issues with the API, contact support through one of these channels:



- Email:[email protected]

[[email protected]](/cdn-cgi/l/email-protection#e794929797889593a79482868b8a8293958e8494c984888a)[Authentication](https://help.sealmetrics.com/en/articles/11124953-authentication)[Login Endpoint](https://help.sealmetrics.com/en/articles/11124976-login-endpoint)[Account Endpoints](https://help.sealmetrics.com/en/articles/11125188-account-endpoints)[Appendix](https://help.sealmetrics.com/en/articles/11125481-appendix)[Implementation Guides](https://help.sealmetrics.com/en/articles/11125557-implementation-guides)[SealMetrics Help Center](/en/)Company

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