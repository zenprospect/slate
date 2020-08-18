# Accounts API

Account is a company your team has explicitly added to your database. It can be from prospected from Apollo, manually added by your team, or created by the API.


## Searching for Accounts

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "sort_by_field": "account_last_activity_date",
    "sort_ascending": false
}' "https://api.apollo.io/v1/accounts/search"
```

> Sample response:

```json
{
    "breadcrumbs": [
        {
            "label": "Company Name",
            "signal_field_name": "q_organization_name",
            "value": "Google",
            "display_name": "Google"
        }
    ],
    "partial_results_only": false,
    "disable_eu_prospecting": false,
    "partial_results_limit": 10000,
    "pagination": {
        "page": 1,
        "per_page": 25,
        "total_entries": 2,
        "total_pages": 1
    },
    "accounts": [
        {
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
            "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/5f2d7f79a697fe0001e115d2/picture",
            "crunchbase_url": "https://www.crunchbase.com/organization/google",
            "primary_domain": "google.com",
            "starred_by_user_ids": [],
            "persona_counts": {},
            "market_cap": "835.5B",
            "organization_raw_address": "1600 Amphitheatre Parkway, Mountain View, CA",
            "organization_city": "Mountain View",
            "organization_street_address": "1600 Amphitheatre Parkway",
            "organization_state": "California",
            "organization_country": "United States",
            "organization_postal_code": "94043",
            "suggest_location_enrichment": false,
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
            "salesforce_record_url": "https://na85.salesforce.com/0011U00000Qyc1CQAR",
            "contact_emailer_campaign_ids": [],
            "contact_campaign_status_tally": {},
            "num_contacts": 12,
            "last_activity_date": null
        }
    ],
    "num_fetch_result": null
}
```

`POST https://api.apollo.io/v1/accounts/search`

Parameter | Description
--------- | -----------
q_organization_name | The account's name
account_stage_ids | An array of stage ids the account must belong to. Refer to /account_stages to get a list of possible stage ids.
sort_by_field | Possible values: "account_last_activity_date" or "account_created_at"
sort_ascending | Possible values: true or false
page | which page to return. Defaults to 1
per_page | how many accounts to return per page. Max = 200

## Getting a List of Account Stages

> Sample request:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/account_stages?api_key=YOUR_API_KEY_HERE"
```

> Sample response:

```json
{
    "account_stages": [
        {
            "id": "5c1004a041f5ac0995d5f5f3",
            "team_id": "5c1004a041f5ac0995d5f5e8",
            "display_name": "Cold",
            "name": "Cold",
            "display_order": 0,
            "default_exclude_for_leadgen": false,
            "category": "in_progress"
        },
        {
            "id": "5c1004a041f5ac0995d5f5f4",
            "team_id": "5c1004a041f5ac0995d5f5e8",
            "display_name": "Current Client",
            "name": "Current Client",
            "display_order": 1,
            "default_exclude_for_leadgen": true,
            "category": "succeeded"
        },
        {
            "id": "5c1004a041f5ac0995d5f5f5",
            "team_id": "5c1004a041f5ac0995d5f5e8",
            "display_name": "Active Opportunity",
            "name": "Active Opportunity",
            "display_order": 2,
            "default_exclude_for_leadgen": true,
            "category": "succeeded"
        },
        {
            "id": "5c1004a041f5ac0995d5f5f6",
            "team_id": "5c1004a041f5ac0995d5f5e8",
            "display_name": "Dead Opportunity",
            "name": "Dead Opportunity",
            "display_order": 3,
            "default_exclude_for_leadgen": false,
            "category": "failed"
        },
        {
            "id": "5c1004a041f5ac0995d5f5f7",
            "team_id": "5c1004a041f5ac0995d5f5e8",
            "display_name": "Do Not Prospect",
            "name": "Do Not Prospect",
            "display_order": 4,
            "default_exclude_for_leadgen": true,
            "category": "failed"
        }
    ]
}
```

`GET https://api.apollo.io/v1/account_stages`


## Updating Account Stage

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "account_ids": ["account_id1", "account_id2"],
    "account_stage_id": "stage_id"
}' "https://api.apollo.io/v1/accounts/bulk_update"
```

> Sample response:

```json
{
    "accounts": [
        {
            "id": "5c3d15a394574686ec3c65d4",
            "account_stage_id": "new_account_stage_id"
        }
    ]
}
```

`POST https://api.apollo.io/v1/accounts/bulk_update`

### Query Parameters

Parameter | Description
--------- | -----------
account_ids | An array of account ids. You can filter for a list of account IDS with the accounts/search API.
account_stage_id | The account stage id to change into. You can GET a list of possible stage ids and its associated information from /account_stages



## Updating Account Ownership

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "account_ids": ["account_id1", "account_id2"],
    "owner_id": "owner_id"
}' "https://api.apollo.io/v1/accounts/update_owners"
```

> Sample response:

```json
{
    "accounts": [
        {
            "id": "5c3d15a394574686ec3c65d4",
            "owner_id": "new_owner_id"
        }
    ]
}
```

`POST https://api.apollo.io/v1/accounts/update_owners`

### Query Parameters

Parameter | Description
--------- | -----------
account_ids | An array of account ids. You can filter for a list of account IDS with the accounts/search API.
owner_id | The owner id to change into. You can GET a list of possible users and its associated information from /users
