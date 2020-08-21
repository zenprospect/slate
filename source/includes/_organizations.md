# Organizations API

An organization represents a company in Apollo's database.

## Enrichment

> Enrich a company's information with just the domain:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/enrich?api_key=YOUR_API_KEY_HERE&domain=google.com"
```


This endpoint enriches a company with info such as industry, company size, etc. based on the domain parameter passed in.

`GET https://api.apollo.io/v1/organizations/enrich`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
domain | The company domain | google.com


## Organization Jobs Postings

> Get a list of active job postings for a company:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/[ORGANIZATION ID]/job_postings?api_key=YOUR_API_KEY_HERE"
```


Get a list of active job postings for a company.

`GET https://api.apollo.io/v1/organizations/[ORGANIZATION ID]/job_postings`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
id | The id of the organization. You can obtain an ID with the company's domain using the enrich endpoint  | 54fca1087369647fcXXXXXXX
