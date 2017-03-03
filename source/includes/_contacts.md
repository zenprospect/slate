# Contacts API

Contact is a person your team has explicitly added to your database. It can be from prospected from ZenProspect, manually added by your team, or created by the API.

## Searching for contacts

> Searching for contacts:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "sort_by_field": "contact_last_activity_date",
    "sort_ascending": false
}' "https://www.zenprospect.com/api/v1/contacts/search"
```

`POST https://www.zenprospect.com/api/v1/contacts/search`

Parameter | Description
--------- | -----------
q_keywords | The contact's name, title, company, or email
contact_stage_ids | An array of stage ids the contact must belong to. Refer to /contact_stages to get a list of possible stage ids.
sort_by_field | Possible values: "contact_last_activity_date", "contact_email_last_opened_at", "contact_email_last_clicked_at", or "contact_created_at"
sort_ascending | Possible values: true or false

## Getting a list of contact stages

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://www.zenprospect.com/api/v1/contact_stages"
```

`GET https://www.zenprospect.com/api/v1/contact_stages`


## Updating Contact Stage
> Update a contact stage:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "contact_ids": ["contact_id1", "contact_id2"],
    "contact_stage_id": "stage_id"
}' "https://www.zenprospect.com/api/v1/contacts/update_stages"
```

`POST https://www.zenprospect.com/api/v1/contacts/update_stages`

### Query Parameters

Parameter | Description
--------- | -----------
contact_ids | An array of contact ids. You can filter for a list of contact IDS with the contacts/search API.
contact_stage_id | The contact stage id to change into. You can GET a list of possible stage ids and its associated information from /contact_stages
