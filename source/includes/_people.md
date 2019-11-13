# People API

A person represents a person in Apollo's database.

## Enrichment

> Enrich a person's information with information:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "first_name": "Tim",
    "last_name": "Zheng",
    "organization_name": "Apollo",
    "email": "tim@apollo.io",
    "domain": "apollo.io"
}' "https://api.apollo.io/v1/people/match"
```



This endpoint enriches a person's information, the more information you pass in, the more likely we can find a match. Each successful enrichment costs a fraction of your lead credits. An enrichment is successful when Apollo returns all of the following information for a person: Name, Linkedin Profile, Current Company Information (Note that an enrichment may charge you credit even without returning an email). Typically this is 0.01 credits per successful enrichment. But it may be higher depending on your specific plan.

`GET https://api.apollo.io/v1/people/match`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
first_name (optional) | The person's first name | Tim
last_name (optional) | The person's last name | Zheng
name (optional) | The person's full name | Tim Zheng
email (optional) | The person's email | tim@apollo.io
organization_name (optional) | The person's company name | Apollo Inc.
domain (optional) | The person's company domain | apollo.io