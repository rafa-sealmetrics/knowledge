# SealMetrics API - Complete Documentation

## Account Endpoints

---

 Api: "GET https://app.sealmetrics.com/api/auth/accounts"

### Overview

The Accounts endpoint provides information about the accounts associated with your API credentials. This endpoint allows you to retrieve account details that can be used in other API requests.

### Request Parameters

#### Headers

| Header          | Value                    | Required    |
| --------------- | ------------------------ | ----------- |
| Authorization   | Bearer your_access_token | Yes         |
| Accept          | application/json         | Yes         |
| Connection      | keep-alive               | Recommended |
| Accept-Encoding | gzip, deflate, br        | Recommended |

#### Query Parameters

This endpoint does not require any query parameters.

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/auth/accounts' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

```json
{
  "status": "ok",
  "data": {
    "000000000000000000001234": "Demo Account"
  }
}
```

#### Response Parameters

The response data object contains key-value pairs where:

- **Key**: Account ID (string)
- **Value**: Account name (string)

---

## Pages Endpoint

---

description: "Get detailed analytics about page views and website traffic"
api: "GET https://app.sealmetrics.com/api/report/pages"

### Overview

The Pages endpoint provides detailed analytics about page views and traffic to your website pages. This endpoint allows you to retrieve metrics such as views, entry pages, and other page-related statistics.

### Request Parameters

#### Query Parameters

| Parameter  | Type    | Required | Description                                                                                |
| ---------- | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id | string  | Yes      | Your account identifier                                                                    |
| date_range | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip       | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit      | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country    | string  | No       | ISO 3166-1 alpha-2 country code filter                                                     |
| utm_medium | string  | No       | Filter by medium (e.g., email, cpc, social media)                                          |
| utm_source | string  | No       | Filter by source (e.g., google, facebook, newsletter)                                      |
| show_utms  | boolean | No       | Flag to display UTM parameters (default: false)                                            |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

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
  ]
}
```

#### Response Parameters

| Field      | Type   | Description                                              |
| ---------- | ------ | -------------------------------------------------------- |
| url        | string | The page URL path                                        |
| views      | number | Total number of page views                               |
| entry_page | number | Number of sessions where this was the first page visited |

---

## Conversions Endpoint

---

description: "Track and analyze conversion events across marketing channels"
api: "GET https://app.sealmetrics.com/api/report/conversions"

### Overview

The Conversions endpoint provides detailed analytics about conversion events on your website. This endpoint allows you to track and analyze sales, sign-ups, or other conversion events across different marketing channels and campaigns.

### Request Parameters

#### Query Parameters

| Parameter    | Type    | Required | Description                                                                                |
| ------------ | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id   | string  | Yes      | Your account identifier                                                                    |
| date_range   | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip         | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit        | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country      | string  | No       | ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)                              |
| utm_medium   | string  | No       | Filter by medium (e.g., email, cpc, social media)                                          |
| utm_source   | string  | No       | Filter by source (e.g., google, facebook, newsletter)                                      |
| utm_campaign | string  | No       | Filter by campaign name                                                                    |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/conversions?date_range=this_month&skip=0&limit=100&account_id=000000000000000000001234' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

```json
{
  "status": "ok",
  "data": [
    {
      "_id": "67eacf47086ba659fa2dd471",
      "amount": 198.09,
      "utm_medium": "email",
      "utm_source": "newsletter",
      "utm_campaign": "newsletter",
      "utm_term": "http://www.rath.org/dolorem-dicta-provident-iusto-quis-ipsam",
      "utm_matchtype": null,
      "country": "es",
      "country_name": "Spain",
      "date": "2025-03-31",
      "label": "sales"
    },
    {
      "_id": "67eacf4301e86b50b10e87a6",
      "amount": 27.24,
      "utm_medium": "cpc",
      "utm_source": "google",
      "utm_campaign": "619999662",
      "utm_term": "Gshopping-194682000766",
      "utm_matchtype": null,
      "country": "es",
      "country_name": "Spain",
      "date": "2025-03-31",
      "label": "sales"
    }
  ]
}
```

#### Response Parameters

| Field         | Type   | Description                                                 |
| ------------- | ------ | ----------------------------------------------------------- |
| \_id          | string | Unique identifier for the conversion                        |
| amount        | number | Monetary value of the conversion                            |
| utm_medium    | string | Medium that drove the conversion (e.g., email, cpc)         |
| utm_source    | string | Source that drove the conversion (e.g., google, newsletter) |
| utm_campaign  | string | Campaign associated with the conversion                     |
| utm_term      | string | Term or URL associated with the conversion                  |
| utm_matchtype | string | Match type for search campaigns (may be null)               |
| country       | string | ISO 3166-1 alpha-2 country code                             |
| country_name  | string | Full name of the country                                    |
| date          | string | Date of the conversion (YYYY-MM-DD)                         |
| label         | string | Type of conversion (e.g., "sales")                          |

---

## Microconversions Endpoint

---

description: "Analyze microconversion events and user engagement patterns"
api: "GET https://app.sealmetrics.com/api/report/microconversions"

### Overview

The Microconversions endpoint provides detailed analytics about microconversion events on your website. Microconversions are small engagement actions that users take before completing a primary conversion, such as adding items to cart, viewing product details, or signing up for newsletters.

### Request Parameters

#### Query Parameters

| Parameter  | Type    | Required | Description                                                                                |
| ---------- | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id | string  | Yes      | Your account identifier                                                                    |
| date_range | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip       | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit      | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country    | string  | No       | ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)                              |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/microconversions?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

```json
{
  "status": "ok",
  "data": [
    {
      "_id": "67eaca8cadeb4e04b13d7df4",
      "date": "2025-03-31",
      "utm_matchtype": null,
      "utm_campaign": "seo-yahoo",
      "utm_source": "seo",
      "utm_medium": "organic",
      "label": "add-to-cart"
    },
    {
      "_id": "67eaca7fba8c162635776cb1",
      "date": "2025-03-31",
      "utm_matchtype": null,
      "utm_campaign": "newsletter",
      "utm_source": "newsletter",
      "utm_medium": "email",
      "label": "newsletter-signup"
    }
  ]
}
```

#### Response Parameters

| Field         | Type   | Description                                                        |
| ------------- | ------ | ------------------------------------------------------------------ |
| \_id          | string | Unique identifier for the microconversion                          |
| date          | string | Date of the microconversion (YYYY-MM-DD)                           |
| utm_medium    | string | Medium that drove the microconversion (e.g., email, organic)       |
| utm_source    | string | Source that drove the microconversion (e.g., seo, newsletter)      |
| utm_campaign  | string | Campaign associated with the microconversion                       |
| utm_term      | string | Term or URL associated with the microconversion                    |
| utm_matchtype | string | Match type for search campaigns (may be null)                      |
| label         | string | Type of microconversion (e.g., "add-to-cart", "newsletter-signup") |

---

## ROAS Evolution Endpoint

---

description: "Track Return on Advertising Spend (ROAS) over time"
api: "GET https://app.sealmetrics.com/api/report/roas-evolution"

### Overview

The ROAS Evolution endpoint provides detailed analytics about Return on Advertising Spend (ROAS) over time. This endpoint allows you to track and analyze the effectiveness of your marketing investments across different channels and campaigns.

### Request Parameters

#### Query Parameters

| Parameter    | Type    | Required | Description                                                                                |
| ------------ | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id   | string  | Yes      | Your account identifier                                                                    |
| date_range   | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip         | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit        | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| time_unit    | string  | No       | Time unit for data aggregation: "daily", "weekly", or "monthly" (default: "daily")         |
| utm_medium   | string  | No       | Filter by medium (e.g., seo, cpc)                                                          |
| utm_source   | string  | No       | Filter by source (e.g., google, newsletter)                                                |
| utm_campaign | string  | No       | Filter by campaign name                                                                    |
| country      | string  | No       | ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)                              |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/roas-evolution?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100&time_unit=daily' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

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
  ]
}
```

#### Response Parameters

| Field            | Type   | Description                                                            |
| ---------------- | ------ | ---------------------------------------------------------------------- |
| \_id             | string | Date or time period identifier (format depends on time_unit parameter) |
| clicks           | number | Number of clicks during the time period                                |
| page_views       | number | Number of page views during the time period                            |
| conversions      | number | Number of conversions during the time period                           |
| microconversions | number | Number of microconversions during the time period                      |
| revenue          | number | Total revenue generated during the time period                         |

---

## Funnel Endpoint

---

description: "Analyze your sales funnel and conversion process"
api: "GET https://app.sealmetrics.com/api/report/funnel"

### Overview

The Funnel endpoint provides detailed analytics about your sales or conversion funnel, showing how users progress through different customer journey stages. This endpoint allows you to analyze conversion rates between stages and identify potential bottlenecks in your funnel.

### Request Parameters

#### Query Parameters

| Parameter   | Type    | Required | Description                                                                                |
| ----------- | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id  | string  | Yes      | Your account identifier                                                                    |
| report_type | string  | Yes      | Type of report to generate (typically "Source")                                            |
| date_range  | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip        | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit       | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country     | string  | No       | ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)                              |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/funnel?account_id=000000000000000000001234&report_type=Source&date_range=20230601,20230630&skip=0&limit=100' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

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
  ]
}
```

#### Response Parameters

| Field            | Type   | Description                                              |
| ---------------- | ------ | -------------------------------------------------------- |
| Source           | string | The source name (or other grouping based on report_type) |
| clicks           | number | Number of clicks from this source                        |
| conversions      | number | Number of final conversions from this source             |
| microconversions | number | Number of microconversions from this source              |
| add-to-cart      | number | Number of add-to-cart actions from this source           |
| checkout         | number | Number of checkout initiations from this source          |

---

## Set-Click Endpoint

---

description: "Record conversion events for offline or external conversions"
api: "POST https://app.sealmetrics.com/api/auth/v1.0/set-click"

### Overview

The Set-Click endpoint allows you to record conversion events associated with user clicks. This endpoint is particularly useful for tracking offline conversions or conversions that happen outside your main website flow, such as phone calls or in-person visits that originated from online marketing efforts.

### Request Parameters

#### Headers

| Header        | Value                             | Required |
| ------------- | --------------------------------- | -------- |
| Authorization | Bearer your_access_token          | Yes      |
| Content-Type  | application/x-www-form-urlencoded | Yes      |
| Accept        | application/json                  | Yes      |

#### Body Parameters

| Parameter      | Type   | Required | Description                                                          |
| -------------- | ------ | -------- | -------------------------------------------------------------------- |
| account_id     | string | Yes      | Your account identifier (must match with your client_id)             |
| url_parameters | object | Yes      | JSON object containing UTM parameters (utm_medium, utm_source, etc.) |
| click_time     | number | Yes      | Timestamp of the click (Unix timestamp in milliseconds)              |
| settings       | object | Yes      | JSON object containing settings like email                           |
| referrer       | string | No       | Referrer URL                                                         |
| current_url    | string | No       | Current URL                                                          |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/auth/v1.0/set-click' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Accept: application/json' \
--data-urlencode 'url_parameters={"utm_medium":"my-medium-01","utm_source":"my-source-01"}' \
--data-urlencode 'click_time=1634707888' \
--data-urlencode 'settings={"email":"user@example.com"}' \
--data-urlencode 'referrer="https://facebook.com/"' \
--data-urlencode 'current_url="https://sealmetrics.com/"' \
--data-urlencode 'account_id=60a52f6ac660b269d13c3f53'
```

### Response

#### Success Response (200 OK)

This request doesn't return any response body when successful.

#### Notes

- This endpoint applies a conversion to the last click of the journey
- You need offline-leads scope enabled in your user account to use this method
- The `account_id` parameter must match with your client_id from your credentials
- The `url_parameters` should include all relevant UTM parameters as a JSON object
- If you want to create a microconversion, include "microconversion":"1" in the lead parameter
- This endpoint is particularly useful for connecting offline conversions with online marketing efforts
- All parameters should be properly URL-encoded when sent in the request

---

## Appendix

---

description: "Glossary, status codes, rate limits, and changelog"

### Glossary of Terms

- **API**: Application Programming Interface
- **Bearer Token**: An authentication token used to access protected resources
- **Conversion**: A completed goal action on your website (e.g., a purchase)
- **Microconversion**: A smaller engagement action that precedes a conversion
- **ROAS**: Return on Advertising Spend
- **UTM Parameters**: Tracking parameters added to URLs (utm_source, utm_medium, etc.)
- **Pagination**: The process of dividing large datasets into smaller chunks or pages
- **Endpoint**: A specific URL that represents an API function or resource

### Status Codes

- **200 OK**: The request was successful
- **400 Bad Request**: The request was invalid or cannot be served
- **401 Unauthorized**: Authentication is required or has failed
- **403 Forbidden**: The server understood the request but refuses to authorize it
- **404 Not Found**: The requested resource could not be found
- **429 Too Many Requests**: Rate limit exceeded
- **500 Internal Server Error**: An error occurred on the server

### Rate Limits

The SealMetrics API implements rate limiting to ensure fair usage and system stability:

- **Starter Plan**: 0 requests per minute
- **Growth Plan**: 1 request per day
- **Enterprise Plan**: 1 request per minute

You'll receive a 429 Too Many Requests response if you exceed these limits. To handle rate limiting gracefully, implement proper retry logic with exponential backoff.

### Changelog

#### Version 1.0 (Current)

- Initial release of the SealMetrics API
- Support for all core analytics endpoints
- Authentication via Bearer token
- JSON response format for all endpoints

---

## Troubleshooting

---

description: "Common errors and debugging tips for SealMetrics API"

### Common Errors

#### Authentication Errors

- **401 Unauthorized**: This typically means your authentication token is invalid or has expired
  - **Solution**: Request a new token using the login endpoint
- **"Invalid credentials"**: This means the email or password provided to the login endpoint is incorrect
  - **Solution**: Verify your credentials and try again

#### Request Errors

- **400 Bad Request**: This usually means there's an issue with your request parameters
  - **Solution**: Check the error message for details about which parameter is missing or invalid
- **404 Not Found**: This means the endpoint URL is incorrect
  - **Solution**: Verify the endpoint URL and ensure it matches the documentation
- **429 Too Many Requests**: This means you've exceeded the rate limit for API requests
  - **Solution**: Implement exponential backoff and retry logic in your code

#### Response Parsing Errors

- **JSON Decode Error**: This occurs when trying to parse a non-JSON response
  - **Solution**: Check if the API returned an error message or if the endpoint doesn't return JSON

### Debugging Tips

1. **Enable Verbose Logging**: Set up detailed logging for API requests and responses to help identify issues
2. **Check Request Headers**: Make sure all required headers are included in your requests
3. **Validate Parameters**: Verify that all required parameters are included and formatted correctly
4. **Test with cURL**: Use cURL commands to test API endpoints directly before implementing in your code
5. **Check Token Expiration**: Ensure your authentication token hasn't expired before making requests

## Implementation Guides

---

description: "Step-by-step guides for implementing SealMetrics API"

### Authentication Implementation Guide

#### Step 1: Obtain API Credentials

Before you can use the SealMetrics API, you need to obtain your API credentials:

1. Contact your account manager or support team to request API access
2. You will receive your API credentials (email and password)
3. Store these credentials securely in your application environment

#### Step 2: Implement the Authentication Flow

```python
import requests
import json
import os
from datetime import datetime, timedelta

# Store credentials securely (e.g., in environment variables)
API_EMAIL = os.environ.get("SEAL_METRICS_EMAIL")
API_PASSWORD = os.environ.get("SEAL_METRICS_PASSWORD")
API_BASE_URL = "https://app.sealmetrics.com/api"

def get_auth_token():
    """
    Authenticate with the API and return a valid token.
    Handles token caching and renewal.
    """
    # Check if we have a cached token
    token_data = load_cached_token()
    if token_data and is_token_valid(token_data):
        return token_data["access_token"]
    
    # If no valid token, request a new one
    url = f"{API_BASE_URL}/auth/login"
    payload = {
        "email": API_EMAIL,
        "password": API_PASSWORD
    }
    headers = {
        "Content-Type": "application/json"
    }
    
    response = requests.post(url, json=payload, headers=headers)
    if response.status_code == 200:
        token_data = response.json()
        # Cache the token
        save_token_to_cache(token_data)
        return token_data["access_token"]
    else:
        raise Exception(f"Authentication failed: {response.text}")

def load_cached_token():
    """Load token from cache if available."""
    try:
        with open(".token_cache.json", "r") as f:
            return json.load(f)
    except (FileNotFoundError, json.JSONDecodeError):
        return None

def save_token_to_cache(token_data):
    """Save token to cache for future use."""
    with open(".token_cache.json", "w") as f:
        json.dump(token_data, f)

def is_token_valid(token_data):
    """Check if the token is still valid."""
    expires_at = datetime.fromisoformat(token_data["expires_at"].replace("Z", "+00:00"))
    # Add a buffer of 5 minutes to ensure we renew before expiration
    return datetime.now(expires_at.tzinfo) < (expires_at - timedelta(minutes=5))

def get_auth_headers():
    """Return headers with authentication token for API requests."""
    token = get_auth_token()
    return {
        "Authorization": f"Bearer {token}",
        "Accept": "application/json",
        "Connection": "keep-alive",
        "Accept-Encoding": "gzip, deflate, br"
    }
```

#### Step 3: Use the Authentication in Your API Requests

```python
def make_api_request(endpoint, params=None):
    """Make an authenticated request to the API."""
    headers = get_auth_headers()
    url = f"{API_BASE_URL}/{endpoint}"
    
    response = requests.get(url, headers=headers, params=params)
    
    if response.status_code == 200:
        return response.json()
    elif response.status_code == 401:
        # Token might be expired, force refresh and try again
        headers["Authorization"] = f"Bearer {get_auth_token(force_refresh=True)}"
        response = requests.get(url, headers=headers, params=params)
        if response.status_code == 200:
            return response.json()
    
    # If we still have an error
    raise Exception(f"API request failed: {response.text}")
```

### Data Retrieval Implementation Guide

#### Step 1: Set Up Your Project

Create a new project and install the required dependencies:

```bash
# Create a new directory for your project
mkdir seal-metrics-integration
cd seal-metrics-integration

# Create a virtual environment (Python)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install required packages
pip install requests python-dotenv
```

#### Step 2: Create Environment Configuration

Create a `.env` file to store your credentials:

```
SEAL_METRICS_EMAIL=user@example.com
SEAL_METRICS_PASSWORD=your_password
SEAL_METRICS_ACCOUNT_ID=your_account_id
```

### Pagination Implementation Guide

When working with large datasets, you'll need to implement pagination to retrieve all records:

```python
def get_all_pages(client, endpoint, params):
    """
    Retrieve all pages of data from a paginated endpoint.
    
    Args:
        client: SealMetricsClient instance
        endpoint: API endpoint path
        params: Base parameters for the request
    
    Returns:
        List of all data items across all pages
    """
    all_data = []
    page_size = params.get("limit", 100)
    current_skip = params.get("skip", 0)
    
    while True:
        # Update skip parameter for current page
        params["skip"] = current_skip
        
        # Make the request
        response = client.make_request(endpoint, params=params)
        
        # Extract data
        data = response.get("data", [])
        
        # If no data or empty list, we've reached the end
        if not data or len(data) == 0:
            break
        
        # Add this page's data to our results
        all_data.extend(data)
        
        # If we got fewer results than the page size, we've reached the end
        if len(data) < page_size:
            break
        
        # Move to the next page
        current_skip += page_size
    
    return all_data
```

### Error Handling Implementation Guide

Implement robust error handling to manage API request failures:

````python
def make_api_request_with_retry(client, endpoint, params=None, max_retries=3, retry_delay=2):
    """
    Make an API request with automatic retries for transient errors.
    
    Args:
        client: SealMetricsClient instance
        endpoint: API endpoint path
        params: Request parameters
        max_retries: Maximum number of retry attempts
        retry_delay: Delay between retries in seconds
    
    Returns:
        API response data
    """
    import time
    
    retries = 0
    last_exception = None
    
    while retries <= max_retries:
        try:
            return client.make_request(endpoint, params=params)
        except Exception as e:
            last_exception = e
            
            # Check if this is a retryable error
            if "rate limit" in str(e).lower() or "timeout" in str(e).lower():
                retries += 1
                if retries <= max_retries:
                    # Wait before retrying, with exponential backoff
                    wait_time = retry_delay * (2 ** (retries - 1))
                    print(f"Retrying in {wait_time} seconds... (Attempt {retries}/{max_retries})")
                    time.sleep(wait_time)
                    continue
            else:
                # Non-retryable error
                raise
    
    # If we've exhausted all retries
    raise Exception(f"Max retries exceeded. Last error: {last_exception}")
```# SealMetrics API - Complete Documentation

## Account Endpoints

---
title: "Account Endpoints"
description: "Retrieve account information associated with your API credentials"
api: "GET https://app.sealmetrics.com/api/auth/accounts"
---

### Overview

The Accounts endpoint provides information about the accounts associated with your API credentials. This endpoint allows you to retrieve account details that can be used in other API requests.

### Request Parameters

#### Headers

| Header | Value | Required |
|--------|-------|----------|
| Authorization | Bearer {your_access_token} | Yes |
| Accept | application/json | Yes |
| Connection | keep-alive | Recommended |
| Accept-Encoding | gzip, deflate, br | Recommended |

#### Query Parameters

This endpoint does not require any query parameters.

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/auth/accounts' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
````

### Response

#### Success Response (200 OK)

```json
{
  "status": "ok",
  "data": {
    "000000000000000000001234": "Demo Account"
  }
}
```

#### Response Parameters

The response data object contains key-value pairs where:

- **Key**: Account ID (string)
- **Value**: Account name (string)

---

## Pages Endpoint

---

## title: "Pages Endpoint"

description: "Get detailed analytics about page views and website traffic"
api: "GET https://app.sealmetrics.com/api/report/pages"

### Overview

The Pages endpoint provides detailed analytics about page views and traffic to your website pages. This endpoint allows you to retrieve metrics such as views, entry pages, and other page-related statistics.

### Request Parameters

#### Query Parameters

| Parameter  | Type    | Required | Description                                                                                |
| ---------- | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id | string  | Yes      | Your account identifier                                                                    |
| date_range | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip       | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit      | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country    | string  | No       | ISO 3166-1 alpha-2 country code filter                                                     |
| utm_medium | string  | No       | Filter by medium (e.g., email, cpc, social media)                                          |
| utm_source | string  | No       | Filter by source (e.g., google, facebook, newsletter)                                      |
| show_utms  | boolean | No       | Flag to display UTM parameters (default: false)                                            |

### Example Request

```bash cURL
curl --location 'https://app.sealmetrics.com/api/report/pages?account_id=000000000000000000001234&date_range=this_month&skip=0&limit=100' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiIsImp0aSI:ImpoaS1Nzg5MzQzIn0...' \
--header 'Accept: application/json'
```

### Response

#### Success Response (200 OK)

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
  ]
}
```

#### Response Parameters

| Field      | Type   | Description                                              |
| ---------- | ------ | -------------------------------------------------------- |
| url        | string | The page URL path                                        |
| views      | number | Total number of page views                               |
| entry_page | number | Number of sessions where this was the first page visited |

---

## Conversions Endpoint

---

## title: "Conversions Endpoint"

description: "Track and analyze conversion events across marketing channels"
api: "GET https://app.sealmetrics.com/api/report/conversions"

### Overview

The Conversions endpoint provides detailed analytics about conversion events on your website. This endpoint allows you to track and analyze sales, sign-ups, or other conversion events across different marketing channels and campaigns.

### Request Parameters

#### Query Parameters

| Parameter  | Type    | Required | Description                                                                                |
| ---------- | ------- | -------- | ------------------------------------------------------------------------------------------ |
| account_id | string  | Yes      | Your account identifier                                                                    |
| date_range | string  | Yes      | Date range for the data (format: YYYYMMDD,YYYYMMDD or predefined values like `this_month`) |
| skip       | integer | No       | Number of records to skip (for pagination), defaults to 0                                  |
| limit      | integer | No       | Maximum number of records to return, defaults to 100 with max value of 100                 |
| country    | string  | No       | ISO 3166-1 alpha-2 country code filter (e.g., "es" for Spain)                              |
| utm_medium | string  | No       | Filter by medium (e.g., email, cpc, social media)                                          |
| utm_source | string  | No       | Filter by source (e.g., google,                                                            |