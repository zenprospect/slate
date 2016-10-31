---
title: ZenProspect API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the ZenProspect API! 

Our API is still in private alpha, is under active development, and is subject to change. Eventually, we plan to make available in the API almost everything you can do in the UI. Additionally, if you have have any suggestions for API methods you'd like to see, please let us know! We would be happy to build it into our API.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: testzenprospectapikey"
```


> Make sure to replace `testzenprospectapikey` with your API key.

ZenProspect uses API keys to allow access to the API. Please contact your dedicated Customer Success Manager for your API key.

ZenProspect expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: testzenprospectapikey`

<aside class="notice">
You must replace <code>testzenprospectapikey</code> with your personal API key.
</aside>

# Prospect API

## Prospect for People

```shell
curl "https://www.zenprospect.com/api/v1/people/search"
  -H "Authorization: testzenprospectapikey"
```


> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves a paginated set of people who matches the specific criteria.

### HTTP Request

`GET https://www.zenprospect.com/api/v1/people/search`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
per_page | 10 | How many results you'd like to return per page. Maximum = 100.
page | 1 | Current page.

<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->

## Prospect for Companies

# Enrich API

## Enrich People 

## Enrich Companies

# Newsfeed API

ZenProspect's Newsfeed API lets you instantly get notifications on any "trigger event", such as a new news article, blog post, job posting, venture funding announcement, and more. There are 2 ways to interact 

1. A webhook component


## Newsfeed Webhooks

## Newsfeed REST API

# Predictive APIs

TODO

# Core REST APIs

## Accounts

TODO


## Activities

TODO

## Calls

TODO

## Contacts

TODO

## Customer Profiles

TODO

## Mailings

TODO

## Sequences

TODO

## Tasks

TODO

## Templates

TODO

## Users

TODO

