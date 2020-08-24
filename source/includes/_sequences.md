# Sequences API

Use the Sequences API to interact with sequences, add contacts to sequence, and more!

## Searching for sequences

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "q_name": "Sequence Name"
}' "https://api.apollo.io/v1/emailer_campaigns/search"
```

> Sample response:

```json
{
    "pagination": {
        "page": 1,
        "per_page": 25,
        "total_entries": 1,
        "total_pages": 1
    },
    "breadcrumbs": [
        {
            "label": "Name",
            "signal_field_name": "q_name",
            "value": "Manual Message Sequence",
            "display_name": "Manual Message Sequence"
        }
    ],
    "emailer_campaigns": [
        {
            "id": "5c8751XXXXXXXXXXXXXXXX",
            "name": "Manual Message Sequence",
            "archived": false,
            "created_at": "2019-03-12T06:27:23.539Z",
            "emailer_schedule_id": "5c1004a041f5ac0995d5f622",
            "max_emails_per_day": null,
            "user_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "same_account_reply_policy_cd": null,
            "excluded_account_stage_ids": [
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX"
            ],
            "excluded_contact_stage_ids": [
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX",
                "5c1004XXXXXXXXXXXXXXXXXX"
            ],
            "contact_email_event_to_stage_mapping": {},
            "label_ids": [],
            "create_task_if_email_open": false,
            "email_open_trigger_task_threshold": 3,
            "mark_finished_if_click": false,
            "active": false,
            "days_to_wait_before_mark_as_response": 5,
            "starred_by_user_ids": [],
            "mark_finished_if_reply": true,
            "mark_finished_if_interested": true,
            "mark_paused_if_ooo": true,
            "sequence_by_exact_daytime": null,
            "permissions": "team_can_view",
            "last_used_at": "2020-04-07T00:34:36.244+00:00",
            "sequence_ruleset_id": "5c1004a041f5ac0995d5f61f",
            "folder_id": null,
            "same_account_reply_delay_days": 30,
            "num_steps": 1,
            "unique_scheduled": 0,
            "unique_delivered": 1,
            "unique_bounced": 0,
            "unique_opened": 1,
            "unique_replied": 0,
            "unique_demoed": 0,
            "unique_clicked": 0,
            "unique_unsubscribed": 0,
            "bounce_rate": 0,
            "open_rate": 1,
            "click_rate": 0,
            "reply_rate": 0,
            "spam_blocked_rate": 0,
            "opt_out_rate": 0,
            "demo_rate": 0,
            "loaded_stats": true,
            "cc_emails": "",
            "bcc_emails": ""
        }
    ],
    "num_fetch_result": null
}
```

`POST https://api.apollo.io/v1/emailer_campaigns/search`


Parameter | Description | Example
--------- | ----------- | -----------
q_name| Name | "Name of Sequence"


## Adding Contacts to Sequence

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "contact_ids": ["contact id 1", "contact id 2"],
    "emailer_campaign_id": REPLACE_WITH_SEQUENCE_ID,
    "send_email_from_email_account_id": "email_account_id",
    "sequence_active_in_other_campaigns": true,
    "sequence_no_email": true,
    "sequence_finished_in_other_campaigns": true,    
}' "https://api.apollo.io/v1/emailer_campaigns/REPLACE_WITH_SEQUENCE_ID/add_contact_ids"
```

> Sample response:

```javascript
// Getting a 404 with this endpoint - not sure whether there is a bug with it or if the code is formatted incorrectly.
```

`POST https://api.apollo.io/v1/emailer_campaigns/REPLACE_WITH_SEQUENCE_ID/add_contact_ids`


Parameter | Description | Example
--------- | ----------- | -----------
id (required, embedded in URL)| ID of the sequence | "583f2f7ed9ced98ab5bfXXXX"
contact_ids (required)| An array of contact Ids | ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
emailer_campaign_id (required)| The ID of sequence to deploy to | "583f2f7ed9ced98ab5bfXXXX"
send_email_from_email_account_id (required)| ID of the email account to send email from, use the email_account/search api to figure out the list IDs | "583f2f7ed9ced98ab5bfXXXX"
sequence_no_email | Whether to still sequence the contact if he/she does not have an email address | true or false (default false)
sequence_active_in_other_campaigns | Whether to still sequence the contact if he/she is active or paused in another sequence | true or false (default false)
sequence_finished_in_other_campaigns  | Whether to still sequence the contact if he/she already finished another sequence | true or false (default false)


## Removing Contacts from Sequence / Marking Contacts as Finished in Sequence

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "emailer_campaign_ids": ["contact id 1", "contact id 2"],
    "contact_ids": ["contact id 1", "contact id 2"],
    "mode": "mark_as_finished"
}' "https://api.apollo.io/v1/emailer_campaigns/remove_or_stop_contact_ids"
```

> Sample response:

```javascript
// Getting a 404 with this endpoint - not sure whether there is a bug with it or if the code is formatted incorrectly.
```

Parameter | Description | Example
--------- | ----------- | -----------
emailer_campaign_ids (required)| A list of ids to remove all contacts from| ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
contact_ids (required)| An array of contact Ids to remove from the sequences | ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
mode (required)| Whether to remove the contacts from the sequence, or mark them as finished | mark_as_finished OR remove