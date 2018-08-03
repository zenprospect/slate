# Accounts API

Account is a company your team has explicitly added to your database. It can be from prospected from Apollo, manually added by your team, or created by the API.


## Searching for accounts

> Searching for accounts:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "sort_by_field": "account_last_activity_date",
    "sort_ascending": false
}' "https://api.apollo.io/v1/accounts/search"
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

## Getting a list of Account Stages

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://api.apollo.io/v1/account_stages"
```

`GET https://api.apollo.io/v1/account_stages`


## Updating Account Stage
> Update a account stage:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "account_ids": ["account_id1", "account_id2"],
    "account_stage_id": "stage_id"
}' "https://api.apollo.io/v1/accounts/bulk_update"
```

`POST https://api.apollo.io/v1/accounts/bulk_update`

### Query Parameters

Parameter | Description
--------- | -----------
account_ids | An array of account ids. You can filter for a list of account IDS with the accounts/search API.
account_stage_id | The account stage id to change into. You can GET a list of possible stage ids and its associated information from /account_stages



## Updating Account Ownership
> Update a account owner:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "account_ids": ["account_id1", "account_id2"],
    "owner_id": "owner_id"
}' "https://api.apollo.io/v1/accounts/update_owners"
```

`POST https://api.apollo.io/v1/accounts/update_owners`

### Query Parameters

Parameter | Description
--------- | -----------
account_ids | An array of account ids. You can filter for a list of account IDS with the accounts/search API.
owner_id | The owner id to change into. You can GET a list of possible users and its associated information from /users
