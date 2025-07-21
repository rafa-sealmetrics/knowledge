---
title: "Login Endpoint"
description: "Authenticate users and obtain access tokens for API requests"
api: "POST https://app.sealmetrics.com/api/auth/login"
---

# Login Endpoint

## Overview

The Login endpoint authenticates users and provides an access token that must be used for all subsequent API requests.

## Endpoint Details

- **Method**: POST
- **URL**: `https://app.sealmetrics.com/api/auth/login`
- **Content-Type**: application/json

## Request Parameters

### Headers

| Header | Value | Required |
|--------|-------|----------|
| Content-Type | application/json | Yes |

### Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| email | string | Yes | Your registered email address |
| password | string | Yes | Your account password |

## Example Request

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

### Success Response (200 OK)

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI6ImpoaS1Nzg5MzQzIn0...",
  "token_type": "Bearer",
  "expires_at": "2025-07-09T18:14:44.000000Z"
}
```

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| access_token | string | JWT token to be used for authentication in subsequent requests |
| token_type | string | Type of token (always "Bearer") |
| expires_at | string | ISO 8601 timestamp indicating when the token will expire |

### Error Response (401 Unauthorized)

```json
{
  "status": "error",
  "message": "Invalid credentials"
}
```

## Notes

- The access token has an expiration time, after which you'll need to request a new token
- Store the token securely and include it in all subsequent API requests
- Do not share your credentials or token with unauthorized parties