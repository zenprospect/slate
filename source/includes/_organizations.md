# Organizations API

An organization represents a company in ZenProspect's database.

## Organization Enrichment

> Enrich a company's information with just the domain:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "domain": "google.com"
}' "https://www.zenprospect.com/api/v1/organizations/enrich"
```


This endpoint enriches a company based on the domain parameter passed in.

`GET https://www.zenprospect.com/api/v1/organizations/enrich`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
domain | The company domain | google.com
