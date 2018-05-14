
# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": [YOUR_API_KEY]
}' "https://www.zenprospect.com/api/v1/auth/health"
```

> If authentication is successful, you should expect to see {"is_logged_in":true}

ZenProspect uses API keys to allow access to the API. Your may request an API key [here](https://www.zenprospect.com/app/#/settings/integrations/api)

ZenProspect expects for the API key to be included in all API requests to the server in as a query string parameter. 

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>
