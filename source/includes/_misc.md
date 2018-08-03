# Misc

## Get a list of users

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://api.apollo/v1/users/search"
```

`GET https://api.apollo/v1/users/search`



## Get a list of email accounts

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://api.apollo/v1/email_accounts"
```

`GET https://api.apollo/v1/email_accounts`

