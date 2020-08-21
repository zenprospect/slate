# People API

A person represents a person in Apollo's database.

## Search

> Search a person's information. Calls to the search endpoint do not cost you credits. They also do not return any email information. To get email information, use the "enrich" endpoint. 


```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "q_organization_domains": "apollo.io\ngoogle.com",
    "page" : 1,
    "person_titles" : ["sales manager", "engineer manager"]
}' "https://api.apollo.io/v1/mixed_people/search"
```    
    

This endpoint searches for people 

`GET https://api.apollo.io/v1/mixed_people/search`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
person_titles (optional) | an array of the person's title. Apollo will return results matching ANY of the titles passed in |  ["sales director", "engineer manager"]
q_organization_domains (optional) | an array of the the company domains to search for, joined by the new line character.  | "google.com\nfacebook.com"
page (optional) | an integer that allows you to paginate through the results  | 1

### Return Results
"people" are people in Apollo's database.
"contacts" are people already in your linked CRM.


## Enrichment

> Enrich a person's information with information:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "id": "583f2f7ed9ced98ab5bfXXXX",
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
id (optional) |  The person's ID obtained from the search endpoint | "583f2f7ed9ced98ab5bfXXXX"