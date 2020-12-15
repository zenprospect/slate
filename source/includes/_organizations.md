# Organizations API

An organization represents a company in Apollo's database.

## Enrichment

> Sample request:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/enrich?api_key=YOUR_API_KEY_HERE&domain=google.com"
```

> Sample response:

```json
{
    "organization": {
        "id": "54fca1XXXXXXXXXXXXXXXXXX",
        "name": "Google",
        "website_url": "http://www.google.com",
        "blog_url": null,
        "angellist_url": "http://angel.co/google",
        "linkedin_url": "http://www.linkedin.com/company/google",
        "twitter_url": "http://twitter.com/google",
        "facebook_url": "https://www.facebook.com/Google",
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
        "logo_url": "https://apollo-server.com/uploads/pictures/5f1aa5XXXXXXXXXXXXXXXXXX/picture",
        "crunchbase_url": "https://www.crunchbase.com/organization/google",
        "primary_domain": "google.com",
        "starred_by_user_ids": [],
        "persona_counts": {},
        "market_cap": "835.5B",
        "industry": "internet",
        "keywords": [
            "software",
            "information technology",
            "search",
            "consumer internet",
            "email",
            "maps",
            "ads",
            "mobile",
            "android",
            "online video",
            "apps",
            "machine learning",
            "virtual reality",
            "cloud",
            "hardware",
            "artificial intelligence",
            "youtube",
            "and software"
        ],
        "estimated_num_employees": 210000,
        "snippets_loaded": true,
        "industry_tag_id": "5567cdXXXXXXXXXXXXXXXXXX",
        "retail_location_count": 1,
        "raw_address": "1600 Amphitheatre Parkway, Mountain View, CA",
        "street_address": "1600 Amphitheatre Parkway",
        "city": "Mountain View",
        "state": "California",
        "postal_code": "94043",
        "country": "United States",
        "owned_by_organization_id": null,
        "suborganizations": [
            {
                "id": "54a11cXXXXXXXXXXXXXXXXXX",
                "name": "drawElements",
                "website_url": "http://www.drawelements.com"
            },
            {
                "id": "54a11eXXXXXXXXXXXXXXXXXX",
                "name": "Pixate, Inc.",
                "website_url": "http://www.pixate.com"
            },
            {
                "id": "54a11fXXXXXXXXXXXXXXXXXX",
                "name": "Anvato",
                "website_url": "http://www.anvato.com"
            },
            {
                "id": "54a122XXXXXXXXXXXXXXXXXX",
                "name": "LabPixies",
                "website_url": "http://www.labpixies.com"
            },
            {
               ...            
            },
        ],            "num_suborganizations": 212,
        "seo_description": "Search the world's information, including webpages, images, videos and more. Google has many special features to help you find exactly what you're looking for.",
        "short_description": "Google's mission ....",
        "annual_revenue_printed": "90.3B",
        "annual_revenue": 90300000000,
        "technology_names": [
            "Gmail",
            "Google Apps",
            "Workday Recruit",
            "Zemanta",
           ...
        ],
        "current_technologies": [
            {
                "uid": "gmail",
                "name": "Gmail",
                "category": "Email Providers"
            },
            {
                "uid": "google_apps",
                "name": "Google Apps",
                "category": "Other"
            },
            {
                "uid": "workday_recruit",
                "name": "Workday Recruit",
                "category": "Recruitment"
            },
            {
                "uid": "zemanta",
                "name": "Zemanta",
                "category": "Content Syndication Networks"
            },
            {
            ...            }
        ],
        "account_id": "5c3d1XXXXXXXXXXXXXXXXXX",
        "account": {
            "id": "5c3d1XXXXXXXXXXXXXXXXXX",
            "domain": "google.com",
            "name": "Google",
            "team_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "typed_custom_fields": {},
            "organization_id": "54fca1XXXXXXXXXXXXXXXXXX",
            "account_stage_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "source": "csv_import",
            "original_source": "csv_import",
            "owner_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "created_at": "2019-01-14T23:05:07.335Z",
            "phone": "(512) 225-6000",
            "phone_status": "no_status",
            "test_predictive_score": null,
            "hubspot_id": null,
            "salesforce_id": "0011UXXXXXXXXXXXX",
            "salesforce_owner_id": "0051UXXXXXXXXXXXX",
            "starred_by_user_ids": [],
            "parent_account_id": null,
            "sanitized_phone": "+15122256000",
            "account_playbook_statuses": [],
            "existence_level": "full",
            "label_ids": [],
            "modality": "account",
            "salesforce_record_url": "https://na85.salesforce.com/0011UXXXXXXXXXXXX",
            "persona_counts": {}
        }
    }
}
```

This endpoint enriches a company with info such as industry, company size, etc. based on the domain parameter passed in.

`GET https://api.apollo.io/v1/organizations/enrich`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
domain | The company domain | google.com


## Organization Jobs Postings

> Sample request:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/ORGANIZATION_ID/job_postings?api_key=YOUR_API_KEY_HERE"
```

> Sample response:

```json
{
    "organization_job_postings": [
        {
            "id": "5ed76XXXXXXXXXXXXXXXX",
            "title": "Product Marketing Manager, Security",
            "url": "https://www.linkedin.com/jobs/view/product-marketing-manager-security-at-google-1878106711?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=14&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
            "city": "San Francisco",
            "state": "California",
            "country": "United States",
            "last_seen_at": "2020-06-03T09:09:57.751+00:00",
            "posted_at": "2020-06-03T07:09:57.751+00:00"
        },
        {
            "id": "5ed768XXXXXXXXXXXXXXXX",
            "title": "Product Marketing Manager, Security",
            "url": "https://www.linkedin.com/jobs/view/product-marketing-manager-security-at-google-1878108613?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=17&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
            "city": "Sunnyvale",
            "state": "California",
            "country": "United States",
            "last_seen_at": "2020-06-03T09:09:57.754+00:00",
            "posted_at": "2020-06-03T07:09:57.754+00:00"
        },
        {
            "id": "5ed768XXXXXXXXXXXXXXXX",
            "title": "Staff Software Engineer, Platforms, Google Cloud",
            "url": "https://www.linkedin.com/jobs/view/staff-software-engineer-platforms-google-cloud-at-google-1878104847?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=18&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
            "city": "Sunnyvale",
            "state": "California",
            "country": "United States",
            "last_seen_at": "2020-06-03T09:09:57.755+00:00",
            "posted_at": "2020-07-30T07:32:24.298+00:00"
        }
    ]
}
```

Get a list of active job postings for a company.

`GET https://api.apollo.io/v1/organizations/ORGANIZATION_ID/job_postings`

### Query Parameters

Parameter | Description | Example
--------- | ----------- | -----------
id | The id of the organization (i.e. NOT account id). You can obtain this with a company's domain by using the enrich endpoint.  | 54fca1087369647fcXXXXXXX
