<!-- 
# People & Organizations API

## Prospect People

```shell
curl "https://api.apollo.io/v1/people/search"
  -H "Authorization: testapolloapikey"
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

`POST https://api.apollo.io/v1/people/search`

### Query Parameters on the Person

Parameter | Description | Example
--------- | ----------- | -----------
ids | Array of people ids to filter by
not_ids | Array of people ids to exclude
q_person_name | String of the person's name. Supports boolean queries.
q_person_title | String of the person's title. Supports boolean queries. | (VP OR Director) AND (Sales OR "Business Development")
person_titles | Array of title keywords you want this person to have. | ["CRO", "CMO"]
person_not_titles | Array of title keywords you want to EXCLUDE 
has_email | String of "yes" or "no" 
has_phone | String of "yes" or "no" 
person_functions | Array of job function tokens. *Possible values*: accounting, sales, operations, finance, marketing, human_resources, information_technology, administrator, legal, engineering, business_development, product_management, consulting, education, administrative, media_and_commmunication, arts_and_design, entrepreneurship. 
person_seniorities | Array of job seniority tokens. *Possible values*: owner, founder, c_suite, partner, vp, head, director, manager, senior, entry, intern
person_locations | Array of location strings for the *persons*'s current location
person_location_name, person_location_radius | If instead you want to search via Location/Zip + Radius, enter a String of location name and a Integer radius expressed in miles


### Query Parameters on the Person's Organization

Parameter | Description 
--------- | ----------- 
organization_ids | Array of organization ids to filter by | 
organization_websites | Array of organization websites to filter by
not_organization_ids | Array of organization ids to exclude | 
not_organization_websites | Array of organization websites to exclude 
organization_locations | Array of location strings for the *organization HQ*'s current location
organization_location_name, organization_location_radius | If instead you want to search via Location/Zip + Radius, enter a String of location name and a Integer radius expressed in miles
currently_using_any_of_technology_uids | Array of technologies the organization is using. Joined by "OR"
currently_using_all_of_technology_uids | Array of technologies the organization is using. Joined by "AND"
currently_using_not_of_technology_uids | Array of technologies the organization is NOT using. Joined by "NOT"
added_technology_uids, added_technology_date_range | Paired set of filters to target organizations who added a set of technologies within a date range.
dropped_technology_uids, dropped_technology_date_range | Paired set of filters to target organizations who dropped a set of technologies within a date range.
organization_has_phone | String of "yes" or "no" to target only organizations for which we have a phone number
organization_latest_funding_stage_cd | Array. Possible values: [:seed, :angel, :venture, :series_a, :series_b, :series_c, :series_d, :series_e, :series_f, :private_equity, :other]
latest_funding_amount_range | Hash of { min: X, max: Y }
latest_funding_date_range | Hash of { min: X, max: Y }
total_funding_range | Hash of { min: X, max: Y }
organization_founded_year_range | Hash of { min: X, max: Y }
organization_domain_status_cd | Array of whether or not the organization's domain supports SMTP verification, is a catch-all domain, or is invalid.
organization_num_employees_ranges | Array of # employee values
organization_linkedin_industry_tag_ids | Array of the "LinkedIn" industry tags
organization_not_linkedin_industry_tag_ids | Array of the "LinkedIn" industry tags to exclude
organization_angellist_market_tag_ids | Array of the AngelList market tags
q_organization_job_titles | String of the job posting titles the company is currently hiring for. Supports boolean queries
organization_job_locations | Array of the location of the job postings




### Other Query Parameters

Parameter | Description 
--------- | ----------- 
include_contact | Boolean. If set to true, the result will return the Apollo contact as an embedded object if the person has already been prospected. Defaults to true.
include_job_postings | Boolean. If set to true, the result will return the company's first 10 job postings as an embedded array. Defaults to false. Refer to the Newsfeed API to find job postings beyond the first 10.
include_newsfeed_events | Boolean. If set to true, the result will return the company's first 10 newsfeed events as an embedded array. Defaults to false. Refer to the Newsfeed API to events beyond the first 10.
per_page | Integer. How many results you'd like to return per page. Possible values: 10, 25.
page | Current page.
prospected_by_current_team | String. "yes', 'no', 'or 'excluded'. Use to filter to new people or people you've already prospected.


## Prospect Organizations

## Enrich People 

Apollo's people enrichment API lets you enter a set of criteria about a person and receive rich information about them. This is useful for:

- Finding the email address of a person when you already have their name + company
- Given an email address of a person, enriching your database with other information like industry, company size, technologies, etc.
- Given a Apollo Person ID, see detailed information about them


### HTTP Request

`POST https://api.apollo.io/v1/people/enrich`

### Query Parameters

Enter as much of the following information as you have available. Our algorithm will smartly pick the fields to optimally find the appropriate person

Parameter | Notes
--------- | ----------- 
id | String. If the Person ID attribute exists, it will override all other attriutes
email | String. If the email exists, we'll use the email as the primary
full_name | String. We can automatically parse out the first/last name from the full name.
first_name | String.
last_name | String. 
company_name | String. Supports boolean queries
company_website | String.
include_contact | Boolean. If set to true, the result will return the Apollo contact as an embedded object if the person has already been prospected. Defaults to true.
include_job_postings | Boolean. If set to true, the result will return the company's first 10 job postings as an embedded array. Defaults to false. Refer to the Newsfeed API to find job postings beyond the first 10.
include_newsfeed_events | Boolean. If set to true, the result will return the company's first 10 newsfeed events as an embedded array. Defaults to false. Refer to the Newsfeed API to events beyond the first 10.
## Enrich Organizations

## Tags
 -->