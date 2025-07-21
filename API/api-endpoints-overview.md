---
title: "API Endpoints"
description: "Overview of available SealMetrics API endpoints and common parameters"
---

# API Endpoints Overview

This section provides detailed documentation for each endpoint available in the SealMetrics API v1.0, including required parameters, optional parameters, example requests, and example responses.

## Common Parameters

Before diving into specific endpoints, let's review the common parameters used across multiple endpoints:

| Parameter | Type | Description |
|-----------|------|-------------|
| account_id | string | Your account identifier (required for most endpoints) |
| date_range | string | Date range for the data in format YYYYMMDD,YYYYMMDD or predefined values |
| skip | integer | Number of records to skip (for pagination), defaults to 0 |
| limit | integer | Maximum number of records to return, defaults to 100 with max value of 100 |
| country | string | ISO 3166-1 alpha-2 country code filter (optional) |
| utm_medium | string | Filter by medium (e.g., email, cpc, social media) |
| utm_source | string | Filter by source (e.g., google, facebook, newsletter) |
| utm_campaign | string | Filter by campaign name |
| show_utms | boolean | Flag to display UTM parameters (default: false) |

## Date Range Options

The `date_range` parameter accepts the following formats:

### Specific Date Range
- Format: `YYYYMMDD,YYYYMMDD`
- Example: `20230601,20230630`

### Predefined Periods
- `today`
- `yesterday`
- `last_7_days`
- `last_14_days`
- `last_30_days`
- `last_60_days`
- `last_90_days`
- `this_month`
- `last_month`
- `this_week_monday_sunday`
- `this_week_sunday_saturday`
- `this_year`
- `last_year`

## Available Endpoints

### Authentication
- **POST** `/auth/login` - Authenticate and obtain access token
- **GET** `/auth/accounts` - Get available accounts

### Reports
- **GET** `/report/acquisition` - Customer acquisition metrics
- **GET** `/report/pages` - Page analytics and traffic
- **GET** `/report/conversions` - Conversion event data
- **GET** `/report/microconversions` - Microconversion analytics
- **GET** `/report/roas-evolution` - ROAS tracking over time
- **GET** `/report/funnel` - Sales funnel analysis

### Data Management
- **POST** `/auth/v1.0/set-click` - Record conversion events

## Response Format

All successful API responses follow this structure:

```json
{
  "status": "ok",
  "data": [
    // Array of result objects
  ]
}
```

## Error Responses

Error responses include status and message information:

```json
{
  "status": "error",
  "message": "Error description"
}
```

## Pagination

For endpoints that support pagination, use the `skip` and `limit` parameters:

- **skip**: Number of records to skip (starts at 0)
- **limit**: Maximum records per request (max 100)

Example pagination through results:
```
First page:  skip=0, limit=100
Second page: skip=100, limit=100
Third page:  skip=200, limit=100
```

## Filtering

Most report endpoints support filtering by:

- **Geographic**: Filter by country using ISO 3166-1 alpha-2 codes
- **UTM Parameters**: Filter by source, medium, campaign, or term
- **Date Range**: Specify time periods for analysis
- **Report Type**: Group data by different dimensions (Source, Medium, Campaign, etc.)

This overview provides the foundation for understanding how to work with SealMetrics API endpoints. Detailed documentation for each specific endpoint follows in subsequent sections.