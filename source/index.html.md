---
title: ZenProspect API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the ZenProspect API! 

Our API is still in private alpha, is under active development, and is subject to change. Eventually, we plan to make available in the API almost everything you can do in the UI. Additionally, if you have have any suggestions for API methods you'd like to see, please let us know! We would be happy to build it into our API.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: testzenprospectapikey"
```


> Make sure to replace `testzenprospectapikey` with your API key.

ZenProspect uses API keys to allow access to the API. Please contact your dedicated Customer Success Manager for your API key.

ZenProspect expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: testzenprospectapikey`

<aside class="notice">
You must replace <code>testzenprospectapikey</code> with your personal API key.
</aside>

# People & Companies API

## Prospect for People

```shell
curl "https://www.zenprospect.com/api/v1/people/search"
  -H "Authorization: testzenprospectapikey"
```


> The above command returns JSON structured like this:

```json
{
   "pagination":{
      "page":1,
      "per_page":10,
      "total_entries":220,
      "next_page":2,
      "previous_page":null,
      "total_pages":22
   },
   "faceting":{
      "prospected_by_current_team_facets":[
         {
            "value":"no",
            "display_name":"Net New",
            "count":155,
            "tooltip":"People you have not prospected"
         },
         {
            "value":"yes",
            "display_name":"Already Prospected",
            "count":65,
            "tooltip":"People from previous lead requests, your CRM, emails, or CSV uploads"
         },
         {
            "value":"excluded",
            "display_name":"Excluded",
            "count":0,
            "tooltip":"People you explicitly excluded"
         }
      ]
   },
   "people":[
      {
         "score":3.0175111,
         "revealed_for_current_team":true,
         "id":"54a3b5a8746869367615770c",
         "first_name":"Mike",
         "last_name":"Huseman",
         "name":"Mike Huseman",
         "linkedin_url":"http://www.linkedin.com/in/mike-huseman-681ba44",
         "title":"Senior Vice President, Global Sales and Business Development",
         "city":"Dallas",
         "email_status":"verified",
         "num_linkedin_connections":500,
         "photo_url":"https://media.licdn.com/mpr/mpr/shrinknp_200_200/p/4/000/13f/2e1/263fbce.jpg",
         "twitter_url":null,
         "github_url":null,
         "facebook_url":null,
         "headline":"Senior Vice President, Global Sales and Business Development @ EnterpriseDB",
         "country":"United States",
         "email":"mike.huseman@enterprisedb.com",
         "state":"TX",
         "contact_id":"56718e10bcc658b367494794",
         "contact":{
            "id":"56718e10bcc658b367494794",
            "first_name":"Mike",
            "last_name":"Huseman",
            "name":"Mike Huseman",
            "linkedin_url":"http://www.linkedin.com/pub/mike-huseman/4/ba4/681",
            "title":"Senior Vice President, Global Sales and Business Development",
            "contact_stage_id":"564aacf79350783b9e000163",
            "owner_id":"577bd3ba7ff0bb70d81ee89e",
            "person_id":"54a3b5a8746869367615770c",
            "email_tickled":true,
            "organization_name":"EnterpriseDB",
            "source":"lead_request",
            "organization_id":"54a1351569702d333de2a500",
            "headline":null,
            "photo_url":null,
            "present_raw_address":"Dallas, Texas, United States",
            "linkedin_uid":"14896321",
            "phone":"(781) 357-3390",
            "sanitized_phone":"+17813573390",
            "extrapolated_email_confidence":0.0,
            "email":"mike.huseman@enterprisedb.com",
            "salesforce_lead_id":"00Q1a000008XlcTEAS",
            "salesforce_contact_id":null,
            "created_at":"2015-12-16T16:15:12.279Z",
            "lead_request_id":"56718c067ff0bb6d07000041",
            "test_predictive_score":null,
            "label_ids":[

            ],
            "emailer_campaign_ids":[
               "5667b33a7ff0bb184000081f"
            ],
            "unlocked":true,
            "last_activity_date":"2015-12-18T17:10:13.362+00:00",
            "email_status":"verified",
            "email_sent":true,
            "email_open":false,
            "email_clicked":false,
            "email_bounced":false,
            "email_replied_positive":false,
            "email_replied":false,
            "custom_fields":{

            },
            "time_zone":"America/Chicago",
            "city":"Dallas",
            "state":"Texas",
            "country":"United States",
            "salesforce_record_url":"https://na24.salesforce.com/00Q1a000008XlcTEAS",
            "salesforce_record_type":"lead",
            "contact_stage":{
               "id":"564aacf79350783b9e000163",
               "name":"Approaching",
               "created_at":"2015-11-17T04:28:39.762Z"
            },
            "account_id":"5660dc1dbcc658b3673e5a29",
            "existence_level":"full"
         },
         "organization":{
            "id":"54a1351569702d333de2a500",
            "name":"EnterpriseDB",
            "website_url":"http://www.enterprisedb.com",
            "blog_url":null,
            "angellist_url":"http://angel.co/enterprisedb",
            "linkedin_url":"http://www.linkedin.com/company/14958",
            "twitter_url":"http://twitter.com/EnterpriseDB",
            "facebook_url":"http://www.facebook.com/EnterpriseDB",
            "image_urls":[
               "https://d2gn4xht817m0g.cloudfront.net/p/product_screenshots/images/original/000/371/769/371769-ac27b11e1969beb82f6d886f6729bd6c74c0543c.?1407426311"
            ],
            "domain":"enterprisedb.com",
            "domain_status":"ticklable",
            "primary_phone":{
               "number":"(781) 357-3390",
               "source":"http://www.enterprisedb.com/"
            },
            "linkedin_industry_tag_cleaned_names":[
               "computer software"
            ],
            "linkedin_specialty_tag_cleaned_names":[
               "open source database",
               "database",
               "postgresql",
               "postgres",
               "oracle compatibility",
               "training",
               "certification",
               "remote dba"
            ],
            "angellist_market_tag_cleaned_names":[
               "open source",
               "business intelligence",
               "big data analytics",
               "hardware + software"
            ],
            "linkedin_company_size_tag_cleaned_names":[
               "201-500 employees"
            ],
            "estimated_num_employees":360,
            "seo_description":"The leader in open source database products, services, support, training and expertise based on PostgreSQL. Free downloads, documentation, and tutorials.",
            "short_description":"EnterpriseDB is the leading worldwide provider of Postgres software and services that enable enterprises to reduce their reliance on costly proprietary solutions and slash their database spend by 80% or more. With powerful performance and security enhancements for PostgreSQL, sophisticated management tools for global deployments and Oracle compatibility, EnterpriseDB software supports both mission and non-mission critical enterprise applications. More than 3,300 enterprises, governments and other organizations worldwide use EnterpriseDB software, support, training and certifications, and professional services to integrate open source software into their existing data infrastructures. Based in Bedford, MA, EnterpriseDB is privately held.\n",
            "city":"Middleborough",
            "state":"Massachusetts",
            "country":"United States",
            "raw_address":"Suite 200 Bedford MA 01730 United States"
         }
      },
   ]
}


```

This endpoint retrieves a paginated set of people who matches the specific criteria.

### HTTP Request

`POST https://www.zenprospect.com/api/v1/people/search`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_contact | true | If set to true, the result will return the ZenProspect contact as an embedded object if the person has already been prospected
per_page | 10 | How many results you'd like to return per page. Possible values: 10, 25.
page | 1 | Current page.

<aside class="success">
</aside>

## Prospect for Companies

# Enrich API

## Enrich People 

## Enrich Companies

# Newsfeed API

ZenProspect's Newsfeed API lets you interact with and get notifications on sales trigger events, such as:

- news article
- blog post
- job posting
- venture funding announcement


There are 2 ways to interact with the Newsfeed API:

1. Webhooks to get real-time updates whenever there's a new Newsfeed Event
2. REST API that lets you query for Newsfeed Events given a certain set of filter criteria


## Newsfeed Webhooks

## Newsfeed REST API

# Predictive API

TODO

# Core REST API

ZenProspect's Core REST API lets you interact with core ZenProspect objects like contacts, accounts, and sequences.

## Accounts

TODO


## Activities

TODO

## Calls

TODO

## Contacts

TODO

## Customer Profiles

TODO

## Mailings

TODO

## Sequences

TODO

## Tasks

TODO

## Templates

TODO

## Users

TODO

