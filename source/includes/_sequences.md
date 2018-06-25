# Sequences API

Use the Sequences API to interact with sequences, add contacts to sequence, and more!

## Searching for sequences

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "q_name": "Sequence Name"
}' "https://www.apollo.io/api/v1/emailer_campaigns/search"
```

`POST https://www.apollo.io/api/v1/emailer_campaigns/search`


Parameter | Description | Example
--------- | ----------- | -----------
q_name| Name | "Name of Sequence"


## Adding Contacts to Sequence
```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "contact_ids": ["contact id 1", "contact id 2"],
    "send_email_from_email_account_id": "email_account_id",
    "sequence_active_in_other_campaigns": true,
    "sequence_no_email": true,
    "sequence_finished_in_other_campaigns": true,    
}' "https://www.apollo.io/api/v1/emailer_campaigns/REPLACE_WITH_SEQUENCE_ID/add_contact_ids"
```

`POST https://www.apollo.io/api/v1/emailer_campaigns/REPLACE_WITH_SEQUENCE_ID/add_contact_ids`


Parameter | Description | Example
--------- | ----------- | -----------
id (required, embedded in URL)| ID of the sequence | "583f2f7ed9ced98ab5bfXXXX"
contact_ids (required)| An array of contact Ids | ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
send_email_from_email_account_id (required)| ID of the email account to send email from, use the email_account/search api to figure out the list IDs | "583f2f7ed9ced98ab5bfXXXX"
sequence_no_email | Whether to still sequence the contact if he/she does not have an email address | true or false (default false)
sequence_active_in_other_campaigns | Whether to still sequence the contact if he/she is active or paused in another sequence | true or false (default false)
sequence_finished_in_other_campaigns  | Whether to still sequence the contact if he/she already finished another sequence | true or false (default false)


## Removing Contacts from Sequence / Marking Contacts as Finished in Sequence
```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "emailer_campaign_ids": ["contact id 1", "contact id 2"],
    "contact_ids": ["contact id 1", "contact id 2"],
    "mode": "mark_as_finished"
}' "https://www.apollo.io/api/v1/emailer_campaigns/remove_or_stop_contact_ids"
```
Parameter | Description | Example
--------- | ----------- | -----------
emailer_campaign_ids (required)| A list of ids to remove all contacts from| ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
contact_ids (required)| An array of contact Ids to remove from the sequences | ["583f2f7ed9ced98ab5bfXXXX", "583f2f7ed9ced98ab5bfXXXX"]
mode (required)| Whether to remove the contacts from the sequence, or mark them as finished | mark_as_finished OR remove