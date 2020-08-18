# People API

A person represents a person in Apollo's database.

## Search 

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "q_organization_domains": "apollo.io\ngoogle.com",
    "page" : 1,
    "person_titles" : ["sales manager", "engineer manager"]
}' "https://api.apollo.io/v1/mixed_people/search"
``` 

> Sample response:

```json 
{
    "breadcrumbs": [
        {
            "label": "Titles",
            "signal_field_name": "person_titles",
            "value": "sales manager",
            "display_name": "sales manager"
        },
        {
            "label": "Titles",
            "signal_field_name": "person_titles",
            "value": "engineer manager",
            "display_name": "engineer manager"
        },
        {
            "label": "Company Domains",
            "signal_field_name": "q_organization_domains",
            "value": [
                "apollo.io",
                "google.com"
            ],
            "display_name": "apollo.io, google.com"
        }
    ],
    "partial_results_only": false,
    "partial_results_limit": 10000,
    "pagination": {
        "page": 1,
        "per_page": 10,
        "total_entries": 1339,
        "total_pages": 134
    },
    "contacts": [],
    "people": [
        {
            "id": "57e1876fa6da987d8411c507",
            "first_name": "Abhilash",
            "last_name": "Mohanty",
            "name": "Abhilash Mohanty",
            "linkedin_url": "http://www.linkedin.com/in/abhilash-mohanty-a3113926",
            "title": "Sales Manager",
            "city": "New York",
            "email_status": "verified",
            "photo_url": "https://media-exp1.licdn.com/dms/image/C4D03AQHUVOFH5VUS8Q/profile-displayphoto-shrink_200_200/0?e=1588809600&v=beta&t=mb0iC9MO2JssEptzNR_Szl0u0-hWcjBzWOalKlIM4lc",
            "twitter_url": null,
            "github_url": null,
            "facebook_url": null,
            "extrapolated_email_confidence": null,
            "headline": "Sales Manager",
            "country": "United States",
            "email": "email_not_unlocked@domain.com",
            "state": "NY",
            "excluded_for_leadgen": false,
            "starred_by_user_ids": [],
            "organization_id": "54fca1087369647fc2010400",
            "organization": {
                "id": "54fca1087369647fc2010400",
                "name": "Google",
                "website_url": "http://www.google.com",
                "blog_url": null,
                "angellist_url": "http://angel.co/google",
                "linkedin_url": "http://www.linkedin.com/company/google",
                "twitter_url": "http://twitter.com/google",
                "facebook_url": "https://www.facebook.com/Google",
                "primary_phone": {
                    "source": "Google",
                    "number": "(512) 225-6000"
                },
                "languages": [
                    "English",
                    "German",
                    "Spanish",
                    "French",
                    "Italian",
                    "Portuguese",
                    "Chinese",
                    "Japanese",
                    "Russian",
                    "English"
                ],
                "alexa_ranking": 1,
                "phone": "(512) 225-6000",
                "linkedin_uid": "1441",
                "publicly_traded_symbol": "GOOG",
                "publicly_traded_exchange": "nasdaq",
                "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/5f1aa5f229ddf50001fa58b9/picture",
                "crunchbase_url": "https://www.crunchbase.com/organization/google",
                "primary_domain": "google.com",
                "persona_counts": {},
                "market_cap": "835.5B"
            },
            "account_id": "5c3d15a394574686ec3c65d4",
            "account": {
                "id": "5c3d15a394574686ec3c65d4",
                "name": "Google",
                "website_url": "http://www.google.com",
                "blog_url": null,
                "angellist_url": "http://angel.co/google",
                "linkedin_url": "http://www.linkedin.com/company/google",
                "twitter_url": "http://twitter.com/google",
                "facebook_url": "https://www.facebook.com/Google",
                "primary_phone": {
                    "source": "Google",
                    "number": "(512) 225-6000"
                },
                "languages": [
                    "English",
                    "German",
                    "Spanish",
                    "French",
                    "Italian",
                    "Portuguese",
                    "Chinese",
                    "Japanese",
                    "Russian",
                    "English"
                ],
                "alexa_ranking": 1,
                "phone": "(512) 225-6000",
                "linkedin_uid": "1441",
                "publicly_traded_symbol": "GOOG",
                "publicly_traded_exchange": "nasdaq",
                "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/5f1aa5f229ddf50001fa58b9/picture",
                "crunchbase_url": "https://www.crunchbase.com/organization/google",
                "primary_domain": "google.com",
                "starred_by_user_ids": [],
                "persona_counts": {},
                "market_cap": "835.5B",
                "domain": "google.com",
                "team_id": "5c1004a041f5ac0995d5f5e8",
                "typed_custom_fields": {},
                "organization_id": "54fca1087369647fc2010400",
                "account_stage_id": "5c1004a041f5ac0995d5f5f3",
                "source": "csv_import",
                "original_source": "csv_import",
                "owner_id": "5c1004a041f5ac0995d5f620",
                "created_at": "2019-01-14T23:05:07.335Z",
                "phone_status": "no_status",
                "test_predictive_score": null,
                "hubspot_id": null,
                "salesforce_id": "0011U00000Qyc1CQAR",
                "salesforce_owner_id": "0051U000001FAqXQAW",
                "parent_account_id": null,
                "sanitized_phone": "+15122256000",
                "account_playbook_statuses": [],
                "existence_level": "full",
                "label_ids": [],
                "modality": "account",
                "salesforce_record_url": "https://na85.salesforce.com/0011U00000Qyc1CQAR"
            }
        }
    ]
}
```

This endpoint searches for people. Calls to the search endpoint do not cost you credits. They also do not return any email information. To get email information, use the "enrich" endpoint.

`POST https://api.apollo.io/v1/mixed_people/search`

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

> Sample request:

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

> Sample response:

```json
{
    "person": {
        "id": "583f2f7ed9ced98ab5bfXXXX",
        "first_name": "Tim",
        "last_name": "Zheng",
        "name": "Tim Zheng",
        "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010",
        "title": "Founder & CEO",
        "city": "San Francisco",
        "email_status": null,
        "photo_url": "https://media-exp1.licdn.com/dms/image/C5603AQGiphGg4YXw4Q/profile-displayphoto-shrink_200_200/0?e=1601510400&v=beta&t=xe-Ju1Oy-Y14Mtf-6catgd5e-0-pnoyto6Xyt2F4tO8",
        "twitter_url": null,
        "github_url": null,
        "facebook_url": null,
        "extrapolated_email_confidence": null,
        "headline": "Founder & CEO at Apollo",
        "country": "United States",
        "email": "tim@apollo.io",
        "state": "CA",
        "excluded_for_leadgen": false,
        "contact_id": "5da8ce2397df39000109c08c",
        "contact": {
            "id": "5da8ce2397df39000109c08c",
            "first_name": "Tim",
            "last_name": "Zheng",
            "name": "Tim Zheng",
            "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010",
            "title": "Founder & CEO",
            "contact_stage_id": "5c48fb36ae29ba0f376d11ab",
            "owner_id": "5c1004a041f5ac0995d5f620",
            "person_id": "5eb53ca9cb371c000148fa81",
            "email_needs_tickling": false,
            "organization_name": "Apollo",
            "source": "search",
            "original_source": "email_import",
            "organization_id": "5e66b6381e05b4008c8331b8",
            "headline": "Founder & CEO at Apollo",
            "photo_url": "https://static-exp2.licdn.com/sc/h/djzv59yelk5urv2ujlazfyvrk",
            "present_raw_address": "San Francisco, California, United States",
            "linkedin_uid": "38777275",
            "extrapolated_email_confidence": 0,
            "salesforce_id": "0031U00001Oe4oWQAR",
            "salesforce_lead_id": null,
            "salesforce_contact_id": "0031U00001Oe4oWQAR",
            "salesforce_account_id": "0011U00001OXEJcQAP",
            "salesforce_owner_id": "0051U000001FAqXQAW",
            "created_at": "2019-10-17T20:25:07.594Z",
            "lead_request_id": null,
            "test_predictive_score": null,
            "emailer_campaign_ids": [],
            "email_manually_changed": false,
            "direct_dial_status": null,
            "direct_dial_enrichment_failed_at": null,
            "email_status": "verified",
            "account_id": "5f1fad1dec295700017e2605",
            "last_activity_date": "2018-06-26T16:30:35.000+00:00",
            "hubspot_vid": null,
            "hubspot_company_id": null,
            "sanitized_phone": null,
            "merged_crm_ids": [],
            "typed_custom_fields": {
                "5d856e9c6899d00098ca4a07": "Tim Zheng"
            },
            "updated_at": "2020-07-28T04:44:51.448Z",
            "queued_for_crm_push": false,
            "starred_by_user_ids": [],
            "suggested_from_rule_engine_config_id": null,
            "label_ids": [],
            "has_pending_email_arcgate_request": false,
            "has_email_arcgate_request": false,
            "existence_level": "full",
            "email": "tim@zenprospect.com",
            "salesforce_record_url": "https://na85.salesforce.com/0031U00001Oe4oWQAR",
            "phone_numbers": [],
            "account_phone_note": null
        },
        "revealed_for_current_team": true,
        "organization_id": "5e66b6381e05b4008c8331b8",
        "organization": {
            "id": "5e66b6381e05b4008c8331b8",
            "name": "Apollo",
            "website_url": "http://www.apollo.io",
            "blog_url": null,
            "angellist_url": null,
            "linkedin_url": "http://www.linkedin.com/company/apolloio",
            "twitter_url": "https://twitter.com/MeetApollo/",
            "facebook_url": "https://www.facebook.com/MeetApollo/",
            "primary_phone": {},
            "languages": [],
            "alexa_ranking": 1955,
            "phone": null,
            "linkedin_uid": "18511550",
            "publicly_traded_symbol": null,
            "publicly_traded_exchange": null,
            "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/5f026534d9225f00016d0505/picture",
            "crunchbase_url": null,
            "primary_domain": "apollo.io",
            "persona_counts": {},
            "industry": "computer software",
            "keywords": [
                "sales engagement",
                "lead generation",
                "predictive analytics",
                "lead scoring",
                "sales strategy",
                "conversation intelligence",
                "sales enablement",
                "lead routing",
                "sales development",
                "and email engagement"
            ],
            "estimated_num_employees": 38,
            "snippets_loaded": true,
            "industry_tag_id": "5567cd4e7369643b70010000",
            "retail_location_count": 0,
            "raw_address": "535 Mission St, Suite 1100, San Francisco, California 94105, US",
            "street_address": "535 Mission St",
            "city": "San Francisco",
            "state": "California",
            "postal_code": "94105",
            "country": "United States",
            "owned_by_organization_id": null,
            "suborganizations": [],
            "num_suborganizations": 0,
            "seo_description": "Apollo is an intelligent, data-first engagement platform that puts structured data at the core of your workflows to help you execute, analyze, and improve on your growth strategy.",
            "short_description": "Apollo is the unified engagement acceleration platform that gives reps the ability to dramatically increase their number of quality conversations and opportunities. Reps are empowered to do more than just conduct outreach, they learn who to target, how to reach out, and what to say at speed and scale. We help drive growth and success by providing the means for teams to discover and utilize their organization's unique best practices. \n\nBy working in a unified platform, reps and managers alike save hours of time each day, strategy changes are instantly scaled across the whole team, and managers can finally dig into data at each step of their pipeline to continually find new ways to improve. \n\nTeams get access to our database of 200+ million contacts with a built-in fully customizable Scoring Engine, full sales engagement stack, our native Account Playbook builder, and the industry's only custom deep analytics suite. Managers create and enforce order and process with the industry's most advanced Rules Engine.\n\nApollo is the foundation for your entire end-to-end sales strategy.\n\nJoin teams like inDesign, Eden, and Gympass to experience the future of sales today. Ready to join our crew? Email sales@apollo.io.",
            "total_funding": null,
            "total_funding_printed": null,
            "latest_funding_round_date": null,
            "latest_funding_stage": null,
            "funding_events": [],
            "technology_names": [
                "Cloudflare DNS",
                "Rackspace MailGun",
                "Gmail",
                "Marketo",
                "Google Apps",
                "Microsoft Office 365",
                "CloudFlare Hosting",
                ...
            ],
            "current_technologies": [
                {
                    "uid": "cloudflare_dns",
                    "name": "Cloudflare DNS",
                    "category": "Domain Name Services"
                },
                {
                    "uid": "rackspace_mailgun",
                    "name": "Rackspace MailGun",
                    "category": "Email Delivery"
                },
                {
                    "uid": "gmail",
                    "name": "Gmail",
                    "category": "Email Providers"
                },
                {
                    "uid": "marketo",
                    "name": "Marketo",
                    "category": "Marketing Automation"
                },
                {
                    "uid": "google_apps",
                    "name": "Google Apps",
                    "category": "Other"
                },
                {
                    "uid": "office_365",
                    "name": "Microsoft Office 365",
                    "category": "Other"
                },
                {
                    "uid": "cloudflare_hosting",
                    "name": "CloudFlare Hosting",
                    "category": "Hosting"
                },
                {
                   ...
                }
            ]
        }
    }
}
```


This endpoint enriches a person's information, the more information you pass in, the more likely we can find a match.  

The enrich endpoint charges credits you for its usage. If a verified email is successfully returned, it will cost you 1 credit. If an email is not found, but Apollo successfully found ALL of the following information: Name, Linkedin Profile, Current Company Information, Apollo will charge a fraction of a credit. Typically this is 0.01 credit per successful enrichment without email. But it may be higher depending on your specific plan.

The enrich endpoint charges credits even if the person is already in your CRM. The enrich endpoint also charges credits if you pass in the same information multiple times.

`POST https://api.apollo.io/v1/people/match`

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