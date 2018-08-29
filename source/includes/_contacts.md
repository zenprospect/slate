# Contacts API

Contact is a person your team has explicitly added to your database. It can be from prospected from Apollo, manually added by your team, or created by the API.

## Create a contact

> Create a contact:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "first_name": "Jon",
    "last_name": "Snow",
    "title": "Lord Commander",
    "organization_name": "Westeros"
}' "https://api.apollo.io/v1/contacts"
```

`POST https://api.apollo.io/v1/contacts`

<aside class="notice">
Apollo enforces strict deduplication during <code>CREATE</code>. If your record contains the same email or name+company as an existing contact, Apollo merges it with the existing record instead of creating a new contact.
</aside>

Parameter | Description | Example
--------- | ----------- | -----------
first_name| First name | "Jon"
last_name | Last Name   | "Snow"
organization_name | Company Name   | "Westeros Inc."
title | Title   | "Lord Commander"
email     | Email. Invalid emails will be ignored.  | "jon.snow@westeros.com"
website_url | The organization website Apollo can use to enrich data for you. DO NOT pass in personal social media urls such as "http://www.linkedin.com/profile_url", or your data will be incorrectly enriched. This argument will be ignored if you pass in a valid email. | "http://www.westeros.com"
label_names | A list of names to tag this newly created contact. If the name does not exist, Apollo will automatically create it | ["inbound contact", "smb clients"]
contact_stage_id | Assign contact to this stage, if the contact does not yet exist. Get a list of possible stage ids with GET /contact_stages | "583f2f7ed9ced98ab5bfXXXX"
present_raw_address | The address string for this contact, Apollo will intelligently infer the city, state, country, and time zone from your address | "San Francisco"


## Update a contact

> Update a contact:

```shell
curl -X PUT -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "first_name": "Jon",
    "last_name": "Snow",
    "title": "Lord Commander",
    "organization_name": "Westeros"
}' "https://api.apollo.io/v1/contacts/YOUR CONTACT ID"
```

`PUT https://api.apollo.io/v1/contacts`

<aside class="notice">
Do not pass in <code>contact_stage_id</code> in this endpoint. Use contacts/update_stages instead.
</aside>

Parameter | Description | Example
--------- | ----------- | -----------
id (Required)        | Contact ID  | "583f2f7ed9ced98ab5bfXXXX"
first_name| First name | "Jon"
last_name | Last Name   | "Snow"
organization_name | Company Name   | "Westeros Inc."
title | Title   | "Lord Commander"
email     | Email   | "jon.snow@westeros.com"
label_names | A list of names to tag this contact. If the name does not exist, Apollo will automatically create it | ["inbound contact", "smb clients"]
present_raw_address | The address string for this contact, Apollo will intelligently infer the city, state, and country from your address | "San Francisco"
direct_phone | The direct dial phone for this contact. If the contact already has a direct dial, this overwrites it. If a contact does not already have a direct dial, this ADDS a new direct dial on top of existing phone numbers | "123-456-7890"
corporate_phone | The corporate phone for this contact. If the contact already has a corporate phone, this overwrites it. If a contact does not already have a corporate phone, this ADDS a new corporate phone on top of existing phone numbers | "123-456-7890"
mobile_phone | The mobile phone for this contact. If the contact already has a mobile phone, this overwrites it. If a contact does not already have a mobile phone, this ADDS a new mobile phone on top of existing phone numbers | "123-456-7890"
home_phone | The home phone for this contact. If the contact already has a home phone, this overwrites it. If a contact does not already have a home phone, this ADDS a new home phone on top of existing phone numbers | "123-456-7890"
other_phone | Phone of unknown type for this contact. If the contact already has phone of unknown type, this overwrites it. If a contact does not already have phone of unknown type, this ADDS a new phone on top of existing phone numbers | "123-456-7890"


## Searching for contacts

> Searching for contacts:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "sort_by_field": "contact_last_activity_date",
    "sort_ascending": false
}' "https://api.apollo.io/v1/contacts/search"
```

`POST https://api.apollo.io/v1/contacts/search`

Parameter | Description
--------- | -----------
q_keywords | The contact's name, title, company, or email
contact_stage_ids | An array of stage ids the contact must belong to. Refer to /contact_stages to get a list of possible stage ids.
sort_by_field | Possible values: "contact_last_activity_date", "contact_email_last_opened_at", "contact_email_last_clicked_at", or "contact_created_at"
sort_ascending | Possible values: true or false
page | which page to return. Defaults to 1
per_page | how many contacts to return per page. Max = 200

## Getting a list of contact stages

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://api.apollo.io/v1/contact_stages"
```

`GET https://api.apollo.io/v1/contact_stages`


## Updating Contact Stage
> Update a contact stage:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "contact_ids": ["contact_id1", "contact_id2"],
    "contact_stage_id": "stage_id"
}' "https://api.apollo.io/v1/contacts/update_stages"
```

`POST https://api.apollo.io/v1/contacts/update_stages`

### Query Parameters

Parameter | Description
--------- | -----------
contact_ids | An array of contact ids. You can filter for a list of contact IDS with the contacts/search API.
contact_stage_id | The contact stage id to change into. You can GET a list of possible stage ids and its associated information from /contact_stages



## Updating Contact Ownership
> Update a contact owner:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "contact_ids": ["contact_id1", "contact_id2"],
    "owner_id": "owner_id"
}' "https://api.apollo.io/v1/contacts/update_owners"
```

`POST https://api.apollo.io/v1/contacts/update_owners`

### Query Parameters

Parameter | Description
--------- | -----------
contact_ids | An array of contact ids. You can filter for a list of contact IDS with the contacts/search API.
owner_id | The owner id to change into. You can GET a list of possible users and its associated information from /users
