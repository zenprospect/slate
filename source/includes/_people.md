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



This endpoint enriches a person's information, the more information you pass in, the more likely we can find a match.  

The enrich endpoint charges credits you for its usage. If a verified email is successfully returned, it will cost you 1 credit. If an email is not found, but Apollo successfully found ALL of the following information: Name, Linkedin Profile, Current Company Information, Apollo will charge a fraction of a credit. Typically this is 0.01 credit per successful enrichment without email. But it may be higher depending on your specific plan.

The enrich endpoint charges credits even if the person is already in your CRM. The enrich endpoint also charges credits if you pass in the same information multiple times.

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