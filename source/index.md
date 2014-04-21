---
title: API Reference

language_tabs:
  - shell
  - ruby
  - perl

toc_footers:
  - <a href='https://tdp.me/account/plus'>API Access requires a subscription</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

---

# Introduction

Welcome to the TDP API!

This is a **work in progress** to enable more customized data collecting and
reporting, as well as automating entry of activities.

# Authentication

> To authorize, use this code:

```ruby
require 'tdp'

api = TDP::APIClient.authorize!('api-token-here')
```

```perl
use Net::TDP;

my $tdp = Net::TDP->new('api-token-here');
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "X-API-Token: api-token-here"
```

> Make sure to replace `api-token-here` with your API key.

TDP uses API keys to allow access to the API. You can register a new TDP API
key under [your account](https://tdp.me/account/api). API Access does require a
TDP Plus subscription, so that [I](http://jayshirley.com) can continue to
operate the service without having to sell one of my children.

TDP expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Access-Token: generatedtoken`

<aside class="notice">
You must replace `generatedtoken` with your personal API key.
</aside>

# Goals

## Get all goals

```ruby
require 'tdp'

api = TDP::APIClient.authorize!('api-token-here')
api.goals.get
```

```perl
use Net::TDP;

my $tdp = Net::TDP->new('api-token-here');
$tdp->goals->get;
```

```shell
curl "https://tdp.me/v1/goals"
  -H "X-Auth-Token: api-token-here"
```

> The above command returns JSON structured like this:

```json
[
  {
                 "id": 177,
               "name": "Goal Name",
             "active": 1,
          "frequency": 1,
           "cooldown": 3,
           "position": 3,
        "category_id": 16,
              "color": "#6D0039",
             "public": 1,
    "quantity_needed": 0,
         "start_date": "2014-04-21T00:00:00",
           "quantity": 1,
        "description": "",
          "reminders": [],
               "tags": [],
     "is_quality_day": 0,
                "rgb": [ 109, 0, 57 ],
       "require_note": 1,
         "foreground": "#000000",
              "trend": [{ "today": 1, "date": "2014-04-21" },...]
  }
]
```

This endpoint retrieves all goals.

### HTTP Request

`GET https://tdp.me/v1/goals`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
range     | 6,1     | Days backwards and forwards to provide in trend data
active    | true    | If set to false, return all goals (even archived and inactive goals)
category  | null    | Pass in a category ID to only return goals in that category.

## Get a specific goal

```ruby
require 'tdp'

api = TDP::APIClient.authorize!('api-token-here')
api.goals.get(1)
```

```perl
use Net::TDP;

my $tdp = Net::TDP->new('api-token-here');
$tdp->goals->get(1);
```

```shell
curl "https://tdp.me/v1/goals/1"
  -H "X-Auth-Token: api-token-here"
```

> The above command returns JSON structured like this:

```json
{
               "id": 177,
             "name": "Goal Name",
           "active": 1,
        "frequency": 1,
         "cooldown": 3,
         "position": 3,
      "category_id": 16,
            "color": "#6D0039",
           "public": 1,
  "quantity_needed": 0,
       "start_date": "2014-04-21T00:00:00",
         "quantity": 1,
      "description": "",
        "reminders": [],
             "tags": [],
   "is_quality_day": 0,
              "rgb": [ 109, 0, 57 ],
     "require_note": 1,
       "foreground": "#000000",
            "trend": [{ "today": 1, "date": "2014-04-21" },...]
}

```

This endpoint retrieves a specific goal.


### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
range     | 6,1     | Days backwards and forwards to provide in trend data
active    | true    | If set to false, return all goals (even archived and inactive goals)
category  | null    | Pass in a category ID to only return goals in that category.


