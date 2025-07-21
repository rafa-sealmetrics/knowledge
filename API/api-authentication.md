---
title: "Authentication"
description: "Learn how to authenticate with the SealMetrics API using Bearer tokens"
---

# Authentication

## Overview

SealMetrics API uses Bearer token authentication to secure all API requests. Before you can access any data endpoints, you must obtain an authentication token through the login process. This token must be included in the Authorization header of all subsequent API requests.

## Login Endpoint

To authenticate with the API and obtain a token, you need to make a POST request to the login endpoint.

**Endpoint:** `https://app.sealmetrics.com/api/auth/login`

### Request Headers

| Header | Value |
|--------|-------|
| Content-Type | application/json |

### Request Body

The login request requires your email and password in JSON format:

```json
{
  "email": "user@example.com",
  "password": "your_password"
}
```

### Example Request

<CodeGroup>

```bash cURL
curl --location 'https://app.sealmetrics.com/api/auth/login' \
--header 'Content-Type: application/json' \
--data-raw '{
  "email": "demo@example.com",
  "password": "demo"
}'
```

```python Python
import requests
import json

url = "https://app.sealmetrics.com/api/auth/login"

payload = json.dumps({
  "email": "demo@example.com",
  "password": "demo"
})

headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)
print(response.text)
```

```javascript JavaScript
const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");

const raw = JSON.stringify({
  "email": "demo@example.com",
  "password": "demo"
});

const requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://app.sealmetrics.com/api/auth/login", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

</CodeGroup>

## Response

Upon successful authentication, the server will respond with a JSON object containing your access token, token type, and expiration information:

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI6ImpoaS1Nzg5MzQzIn0...",
  "token_type": "Bearer",
  "expires_at": "2025-07-09T18:14:44.000000Z"
}
```

## Using the Token

For all subsequent API requests, you must include the obtained token in the Authorization header using the Bearer scheme:

### Required Headers for Authenticated Requests

| Header | Value |
|--------|-------|
| Authorization | Bearer {your_access_token} |
| Accept | application/json |
| Connection | keep-alive |
| Accept-Encoding | gzip, deflate, br |

### Example Authenticated Request

```bash
curl --location 'https://app.sealmetrics.com/api/report/acquisition?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json' \
--header 'Connection: keep-alive' \
--header 'Accept-Encoding: gzip, deflate, br'
```

## Token Expiration and Renewal

The authentication token has an expiration time, which is included in the `expires_at` field of the login response. To maintain uninterrupted access to the API, you should:

1. Store the expiration time along with the token
2. Check the token's validity before making API requests
3. If the token is expired or about to expire, request a new token using the login endpoint
4. Update your stored token with the new one

## Security Best Practices

To ensure the security of your API access:

1. **Never hardcode credentials** in your application code
2. **Store API credentials securely** using environment variables or a secure credential manager
3. **Implement proper error handling** for authentication failures
4. **Set up automatic token renewal** before expiration
5. **Use HTTPS** for all API communications
6. **Limit access** to your authentication token within your application
7. **Implement proper logging** for authentication events for audit purposes

## Troubleshooting Authentication Issues

If you encounter authentication problems:

- **401 Unauthorized**: Verify that you're using the correct email and password
- **Token Expired**: Check if your token has expired and request a new one
- **Invalid Token Format**: Ensure you're correctly formatting the Authorization header
- **Connection Issues**: Verify your network connection and the API service status

If problems persist, please contact SealMetrics API support with details about the specific error messages you're receiving.