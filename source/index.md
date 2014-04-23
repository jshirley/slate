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
  - goals
  - completion
  - stats
  - reminders
  - reports
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


