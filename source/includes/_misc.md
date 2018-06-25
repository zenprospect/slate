# Misc

## Get a list of users

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://www.apollo.io/api/v1/users/search"
```

`GET https://www.apollo.io/api/v1/users/search`



## Get a list of email accounts

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE"
}' "https://www.apollo.io/api/v1/email_accounts"
```

`GET https://www.apollo.io/api/v1/email_accounts`

