# Requests

> Sample response:

```json
{
    "x-daily-requests-left": "the total requests left for the current 24 hour period",
    "x-daily-usage": "the total requests used for the current 24 hour period",
    "x-hourly-requests-left": "the total requests left for the current 60 minute period",
    "x-hourly-usage": "the total requests used for the current 60 minute period",
    "x-minute-requests-left": "the total requests left for the current 60 second period",
    "x-minute-usage": "the total requests used for the current 60 second period",
    "x-rate-limit-daily": "based on your plan",
    "x-rate-limit-hourly": "based on your plan",
    "x-rate-limit-minute": "based on your plan"
}
```

Requests to our API will be limited in accordance with your current pricing plan (detailed [here](https://www.apollo.io/pricing/#compare-plans) under Compare Plans > CRM > API Access).

To view how many requests your current plan allows, as well as how many requests you have used, you can reference the headers of a successful response from the API. See the sample response to the right for more detail.

