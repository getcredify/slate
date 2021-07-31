---
title: Credify API Docs

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: curl
  - ruby: Ruby
  - python: Python
  - javascript: Javascript

toc_footers:
  - <a href='https://getcredify.com'>Sign Up for an API Key</a>
  - <a href='https://documenter.getpostman.com/view/5027621/TzseKmQn'>View Postman Examples</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Credify API!

# Authentication

- API Key (Client ID)

Parameter Name: x-credify-client-id, in: header. Your Credify API Client ID

- API Key (Client Secret)

Parameter Name: x-credify-client-secret, in: header. Your Credify API Client Secret

# Pulls

## Get Pull By ID

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-credify-client-id' => 'CLIENT_ID',
  'x-credify-client-secret' => 'CLIENT_SECRET'
}

result = RestClient.get 'https://api.getcredify.com/v1/pulls/{pullId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-credify-client-id': 'CLIENT_ID',
  'x-credify-client-secret': 'CLIENT_SECRET'
}

r = requests.get('https://api.getcredify.com/v1/pulls/{pullId}', headers = headers)

print(r.json())
```

```shell
# You can also use wget
curl -X GET https://api.getcredify.com/v1/pulls/{pullId} \
  -H 'Accept: application/json' \
  -H 'x-credify-client-id: CLIENT_ID' \
  -H 'x-credify-client-secret: CLIENT_SECRET'
```

```javascript
const headers = {
  Accept: "application/json",
  "x-canopy-client-id": "CLIENT_ID",
  "x-canopy-client-secret": "CLIENT_SECRET",
};

fetch("https://api.getcredify.com/v1/pulls/{pullId} ", {
  method: "GET",

  headers: headers,
})
  .then(function (res) {
    return res.json();
  })
  .then(function (body) {
    console.log(body);
  });
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "message": "Pull successfully retrieved",
  "data": {
    "pull": {
      "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
      "has_mfa": false,
      "status": "SUCCESS",
      "consumer_verified": true,
      "pdf_report": "https://s3.amazonaws.com/credify.dev/pulls/c6f3e62f-ed0c-4266-8014-e7dbd417cbfc/report.pdf?AWSAccessKeyId=AKIAVP2XBDEX4CHSFJ6G&Expires=1627733762&Signature=73OWSAOq%2FRKMj8Wi97U5cH50WtM%3D",
      "credit_score_histories": [
        {
          "credit_score_history_id": "7c588459-9848-406b-aa7b-da167d45e72d",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-07-06T01:59:49.000Z",
          "value": 757,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "038b608f-9ca0-403f-a9a1-87453d18487b",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-06-27T02:26:52.000Z",
          "value": 757,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "6565ddd8-eae1-49e4-a6eb-798c0e8290c2",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-06-13T12:31:21.000Z",
          "value": 757,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "c41d7a6a-31f1-44c6-a224-4a28459c950a",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-05-31T02:03:11.000Z",
          "value": 753,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "1789b5c3-095a-4de0-a55f-bca162d83140",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-05-15T23:12:04.000Z",
          "value": 753,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "8eddbe8c-2ac0-4b21-af69-c26a2c48aafe",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-04-25T00:38:08.000Z",
          "value": 759,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "6d393834-0ead-46a0-a736-21c5dc47a871",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-03-24T15:56:54.000Z",
          "value": 751,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "34cc40a1-b012-4216-b415-0bc6c11c96fc",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-03-06T18:20:20.000Z",
          "value": 720,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "cc12d474-f18e-43ac-8f9f-0e291432d1fe",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-02-22T22:48:16.000Z",
          "value": 720,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "774d6950-8bad-4c16-b87e-02e44c1531c5",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-02-11T11:48:29.000Z",
          "value": 720,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "e5f01496-c239-4391-8f07-e57a1bd17d8e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-31T23:34:23.000Z",
          "value": 723,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "ef6269a6-03a3-4d1f-aac3-c2658e37a578",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-22T20:39:39.000Z",
          "value": 723,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "171c729c-3735-4fc1-a7b9-35a8fc0aa9aa",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-08T14:55:57.000Z",
          "value": 714,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "ab271320-8aeb-4bbc-a6af-0ecc9a546f87",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-12-29T06:32:12.000Z",
          "value": 714,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "2e5ce1b1-6996-4c3a-ba2f-92e70d50077b",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-12-07T18:53:13.000Z",
          "value": 717,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "d6505474-d1ba-49e7-8fe9-a74cdee8b075",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-11-30T21:46:32.000Z",
          "value": 717,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "1e573f71-189f-4c49-bba8-7c1c06d4842b",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-08-26T23:19:18.000Z",
          "value": 717,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "fe8be597-1d82-4f65-9144-2463b85b383e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-08-19T22:39:52.000Z",
          "value": 717,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "7206f2f9-8785-4b9d-9b1b-5db68d8a6123",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-07-20T12:29:33.000Z",
          "value": 715,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "e900978b-7d7b-4d53-af6c-1ff1f7157c95",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-07-09T22:57:16.000Z",
          "value": 715,
          "bureau": "EQUIFAX"
        },
        {
          "credit_score_history_id": "aee7f6d4-9a8d-4cad-abab-631cd65bc336",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-07-06T01:59:50.000Z",
          "value": 757,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "262e39f7-3b8d-4c3e-b370-6ddedde25d77",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-06-27T02:26:53.000Z",
          "value": 757,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "4be30fb3-2919-4a05-beaf-a5dd541adca1",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-06-13T12:31:22.000Z",
          "value": 757,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "9ea26456-4d9a-400e-8731-3d8f5efcb5d3",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-05-31T02:03:12.000Z",
          "value": 753,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "c9a849f9-355e-4c36-a4f1-033e76369698",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-05-15T23:12:04.000Z",
          "value": 753,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "ee962ecd-4316-4675-a3d9-e6ec448e441d",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-04-25T00:38:08.000Z",
          "value": 759,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "bbabb33d-f099-4f41-8a15-86ea8987cff8",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-03-29T11:58:42.000Z",
          "value": 751,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "abe3d859-e1af-4943-bf2a-c663f8d03f75",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-03-24T15:56:54.000Z",
          "value": 723,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "7c4ab726-c02e-4ec6-aad6-4385a232fd20",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-03-06T18:20:20.000Z",
          "value": 720,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "609a4820-011b-4143-9cc7-60ae220a37a8",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-02-22T22:48:17.000Z",
          "value": 720,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "d0a880ec-9857-4d2c-b010-6790ce795c53",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-02-11T11:48:26.000Z",
          "value": 720,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "d064c2e1-701f-4906-9ddf-a6df8262bc2e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-31T23:34:23.000Z",
          "value": 723,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "94b18d9b-ea3a-4d77-a19b-87abbdef6066",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-22T20:39:39.000Z",
          "value": 723,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "464c20c6-75ff-476c-a409-450194ffb4a5",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2021-01-08T14:55:59.000Z",
          "value": 713,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "6137643e-e28a-4ab7-b944-f6e5219fcaa7",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-12-29T06:32:12.000Z",
          "value": 713,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "85e6b8f4-28d7-49c2-b960-77d355700932",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-12-07T18:53:14.000Z",
          "value": 717,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "91d4304f-767c-43cd-ba90-5758b3bf6a6d",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-11-30T21:46:32.000Z",
          "value": 716,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "0ecca933-ec54-4e18-ab2e-468f6f2ea42a",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-08-26T23:19:18.000Z",
          "value": 717,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "0516dc34-3a0a-48e7-8a7f-c55983db39f2",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-08-19T22:39:53.000Z",
          "value": 717,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "81f987d5-cb57-4fc3-b409-da2f121b2988",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-07-20T12:29:34.000Z",
          "value": 714,
          "bureau": "TRANSUNION"
        },
        {
          "credit_score_history_id": "c611732e-2fc7-40de-9622-f3cd47843e21",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "date_reported": "2020-07-09T22:57:17.000Z",
          "value": 714,
          "bureau": "TRANSUNION"
        }
      ],
      "accounts": [
        {
          "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "CAPITAL ONE BANK USA NA",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2016-12-09T05:00:00.000Z",
          "term": null,
          "open_balance_cents": null,
          "balance_date_reported": "2021-06-07T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 350000,
          "minimum_monthly_payment_cents": 2500,
          "monthly_payment_cents": 2500,
          "last_payment_date": "2021-06-02T04:00:00.000Z",
          "worst_payment_status": "30-59 Days Late",
          "remarks": null,
          "times_30_days_late": 2,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "CAPITAL ONE BANK USA NA",
          "institution_address_line_2": "PO BOX 31293",
          "institution_city": "SALT LAKE CITY",
          "institution_state": "UT",
          "institution_zipcode": "84131",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "d733ee4b-b407-44e3-b504-1a723463cf87",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 12,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7521fac3-f53c-4853-b405-428f30d84671",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 11,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "62e9e449-8483-4ea0-93b3-ed1f281250ea",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 10,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8f2234ed-58b3-4804-874c-4b9f6c4d4b90",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 9,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fdd27bfd-180d-46a3-ac60-18375f133d67",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 8,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cbd60035-9ee3-46a5-8337-d059394a2904",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 7,
              "year": 2017,
              "status": "NOT_CURRENT"
            },
            {
              "account_payment_history_id": "0111d503-4d5b-43ee-85dc-c09f884cf63d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 6,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0eadde06-caf5-40ef-9d73-26d2d9d57099",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "be2e0257-375b-4c18-aaad-eccda7aa2395",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4ff8bd21-2c87-43a6-b73d-abd4a5b02b61",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ceb2ebd4-69e8-4116-bbdc-a8bb76dc6d6d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "64f5ac75-878b-4b18-9bd9-a006f9783f30",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 8,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c26a4182-1ffb-41ff-824b-ab39e8a235cf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 7,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b97ebbe6-7f32-4521-9f06-af1259b95ff1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 6,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cb9f5b68-0527-4c0d-bc3f-af4b03b8256b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 5,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5e641a4b-7e67-4356-98b8-1937d0d16175",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 4,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b0f72f34-bf92-46f2-bf8a-dcd8a0b180a5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 3,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1551a673-436b-4d0c-99d0-57daf8e2d969",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 2,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6cdcd936-a2ec-4d8f-ac50-b86fb6406165",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 1,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "38b03e19-a38f-46e8-8699-053db8439daa",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f8a75976-1e26-499e-bdd1-15b1ef78c8cd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0121c58e-908c-4c30-b7ca-8268770b77a5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0391c2f9-dd01-4d50-81a5-3e2f39717b9d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4b266aba-357b-4c30-b188-fb5d46cd8663",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6a2a3717-17ec-4911-b409-7f7271433ee3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "71a837bb-7e7f-4b1d-a753-0c9ebcb42701",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "33f74d12-7849-44f9-9067-d4a52e1eb178",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fbc45230-f3f2-4780-ac29-7a7928338130",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2ba48c37-9ab5-4d61-990a-1312c055a777",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 3,
              "year": 2019,
              "status": "NOT_CURRENT"
            },
            {
              "account_payment_history_id": "331a2a49-ce3a-4e5a-bbed-be1753d10064",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e2379735-6ec2-4579-95de-869aa06b642a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c560e5bc-2fbb-4aea-8f89-bcce0d3c0e84",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "faecaee4-003e-43cf-aad3-3d464bedb8ed",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "99462a3d-ce20-41da-97ce-4f2fd42b6227",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cd757824-5159-4bb2-9035-b0dfd21c7963",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3891739f-9768-477c-8d8a-3ef09ffccec3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0faf5184-c8e3-4669-be38-cfc33b356d9f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7fa5b590-3194-4a27-bfb1-de0597cddc3f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "741a77b6-e5ac-405e-be45-02c8e5cf54ed",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "37b085cc-390c-4db8-be50-9ef25109ad46",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ef28fbd7-282f-402b-87ea-2852307b2f3d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "07ed70c6-02f7-4da9-aa4c-628c1e830e83",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "31591045-73cd-4cbb-8cf6-8e517287602d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bdb42a2c-3077-4af8-958b-6fae3e318fbb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "07b097b4-1f8c-471f-a8ca-31b939d2d670",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "47bad73c-6f72-4c10-af62-3e6b8fded01c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "82b929d3-33b1-41fa-bafa-b62ec6ddc5ee",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a8c6b04f-73eb-40b2-ab8c-07fb6dc7d0f5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e46f0326-0406-4849-aa51-5b3569b24268",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FEDLOAN SERVICING",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2015-11-09T05:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 263300,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 350000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FEDLOAN SERVICING",
          "institution_address_line_2": "POB 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "64849e07-b03b-4241-9e59-9355f2f475c5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ab8b19b9-82e3-493c-bfb0-ad78f240f137",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "93cdecec-3e04-4287-91d3-e06d70da8bdd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "01f0b1f4-9e64-43ee-99aa-8103fa23a13c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d836f1e6-7d51-4389-8b92-55996a604797",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "277f195f-2f99-49ec-86a2-7fc569e06807",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f171af5a-ccf4-453c-81bb-5ace8f97bcc8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d2da8642-9b18-4273-ad6a-61cd4c75a954",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "018e5e5f-211e-4104-9513-e5e5edca6729",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b54caee9-4fe3-46e6-8c4c-364dad06119b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "30ae24e0-b388-45c2-a504-1751588259ac",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "548e8427-bb7d-4600-a1a7-e4cbf194ff3a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1b092b48-c0b2-4af9-9796-860ea4658a9b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "dde201ab-adb5-4460-b195-591175cac32a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a181e764-32cf-48e1-b54b-5f9ad8496df2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ce33d1f9-c8ec-4632-8749-535b43f54066",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9403f386-51e1-4abb-84ea-747faf62c54e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ab2cf191-21c2-4a7e-a686-62528ecf5c54",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "34ddefbd-b8a8-44f0-8fed-48ea7f4d4315",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f54a233e-6534-403e-af3d-767edffccb63",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ee311a02-b12b-4e4b-a51e-c9f140218808",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "197253fc-3cfd-4363-8f92-ac64ca510148",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c489973b-7cfa-49d9-907b-ab56ce354756",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FEDLOAN SERVICING",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2016-08-30T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 165900,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 200000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FEDLOAN SERVICING",
          "institution_address_line_2": "POB 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "2c648c9e-b961-4e65-bf42-b5db0ca7e2c4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4346b905-a5c0-4393-82b1-1dc21b0198bd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ac1ddc0e-a631-43d7-89df-078f68ddfe98",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "40e21e3e-16e8-4150-98e4-9667d6de8e39",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f147fe4e-3bcf-4950-a30e-6d7adc590d56",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "60c8ea15-7266-4455-8be4-9985f0c18474",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "eaf9ccf2-f6fb-444a-b1e4-2a0df8114c97",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e0c0d4a4-67cc-4244-90c9-3f1ddcad8fce",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f0473379-cbde-4298-9a95-e7be7c66b48a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d2a28ba0-ac05-4552-a410-262551d8dfce",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bbba1da6-f4e5-469e-bb67-79d6f5d2cc52",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "52dc59e6-6584-491d-8e9d-7a0cc47acfbc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "99e1f783-1185-434d-bb42-5363c8ad85ae",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "85c937a0-f5b4-4621-a5f7-deffaf67e169",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "76b6b434-d1ed-481a-b423-f7a313d11e0c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "594e1667-c7d5-488b-92d5-389e3e0778ec",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e1225f4c-604b-43de-a4f2-289884925f32",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7e753641-5136-407a-b920-95f351a6ade4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6cfbe51f-1542-45e3-b8a2-32de6bf809bf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5a677ef3-ed1d-44aa-9dba-8d8cb78cf346",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9a5f55af-3ca5-4bca-b41b-e6dc9b09620a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ebf58806-faab-4666-bc83-84f0859f8a79",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "f89c2509-0739-44b8-8d3e-ea7d941af817",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "CAPITAL ONE BANK USA NA",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2017-09-05T04:00:00.000Z",
          "term": null,
          "open_balance_cents": null,
          "balance_date_reported": "2021-06-19T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 1500000,
          "minimum_monthly_payment_cents": 2500,
          "monthly_payment_cents": 2500,
          "last_payment_date": "2021-06-08T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "CAPITAL ONE BANK USA NA",
          "institution_address_line_2": "PO BOX 31293",
          "institution_city": "SALT LAKE CITY",
          "institution_state": "UT",
          "institution_zipcode": "84131",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "c083518b-00a0-46b9-9dc2-9971b6fc7f62",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 12,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "77da19b9-325f-4157-a09a-eaf13f9546fb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 11,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9f71e293-b122-4405-a84c-a1845f5b09e1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 10,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e8c6563c-99f6-4922-81d1-84ddacb7a120",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fe3e78ba-74ea-43ba-8675-f8c09cc8d9e8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1296af25-9626-45c9-8c64-c07a790ae4fd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1d929d4c-c2d3-4955-b456-b9c0ee6effb6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ee490109-a6e0-4f6f-a5c3-efdb9832272e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 8,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b6a340b6-cd1c-487c-bfc5-2c2786526f68",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 7,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bf22aad9-0aed-4c5c-9555-2a45d93ca0cf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 6,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d5bc1be9-e519-41d0-8fde-0efd7501fd5a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 5,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "62e93411-cbff-47dd-8dfc-48d1e9f3368d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 4,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bb993cb1-c8a2-4ea0-afe8-031954b632b7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 3,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1cf76c90-4444-4cbf-b88f-4bd76e79582d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 2,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "519d742c-c044-47e3-a989-44d91be4a076",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 1,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2b6c4863-b6ae-42e7-8d2c-c99f785fba4e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2fd40bc7-aa0e-40c7-8a20-c9827ad93622",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ab6baca9-6f9c-4e08-b7c4-b0cf762f4589",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4d2244d5-244f-49b5-85b9-9627206c40a3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3d9222f4-e840-4eb2-949a-bc2fdb368a04",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5327fb3f-e48a-4149-b066-d18703751110",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2fcb8ec0-7501-4a87-af50-79d81ea5b96a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b6bce44e-ef5b-4be5-9e8e-d101ee73b4ac",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "94c3cb29-f1f8-48f0-be25-03667bd95239",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "20709542-6a36-4466-944c-3a19b8f19ac7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 3,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6085dba7-78ce-4cae-9243-64b4efe81476",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "85ba5daa-d665-475a-a730-ce03659421fd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6da19473-95b5-4055-801b-a540d4413198",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a4717a1b-72b1-4897-9771-6241532fb561",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ac1e9c5f-3241-4535-9418-d4de0312f2eb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cd1d7c9c-641c-4dde-a44f-d455cf71b404",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2c6dbe61-06a7-4c9c-891f-173f1ea3ae34",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9dca8a52-ad6a-4120-84c7-04ca7d2536d1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3b954a9c-8612-432c-97fd-77a878ed513b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "483c219b-da77-4031-a33f-f8b302412570",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d090e759-b323-4646-b5f6-43421d93eaf5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c029f367-6647-4500-a467-bfedaf67d578",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1f171561-a952-4394-8970-4fe9382869a8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "280bf496-b8e4-43b9-977d-f95565708300",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "40ba1dfb-6a00-4805-9452-64ec4264f872",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e54fc1eb-4f4a-4a00-8ace-ebfa4a17aa5f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f642001f-21b2-47a7-8165-ee3ea83d2d93",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a2d49cf3-0252-4bcc-bb93-9ce4032f9616",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "94342bff-3836-4db7-b606-c3add3806b38",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "c9259ffe-17ce-4ded-9b9a-5f3dd896bd46",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FEDLOAN SERVICING",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2015-11-09T05:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 173100,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 200000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FEDLOAN SERVICING",
          "institution_address_line_2": "POB 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "210bf5c9-d388-48a8-b310-a9cb5527650a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "18aa8da4-2412-4fa3-b114-44d5162d9b3f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "59b2bfb5-ae10-4322-bc72-8eb0cd06b689",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b2fa9a2d-516f-4e9c-bbcc-e6feb2663c37",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1c1fe878-9c7b-4428-b09c-78b8703b97ae",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c6e3880a-7734-4487-a707-a19fe293ab93",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9cff8952-c59e-4d2d-9cf9-0ca6ec975a9f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b3ff6acd-1ea5-44f7-a19a-10896edfb45d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "39d515f7-6579-4196-a791-8cbbed56e457",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b415763e-682d-4e39-a85e-e5577e10a2c8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d81b8203-4632-4317-b6a8-fd0030ee162b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1af73a74-2e38-4923-a1d0-782255c90c1a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "094ff19c-c405-46f7-aa6f-dbd8ba004abf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cb99c211-3e38-4776-bb70-436b50394f48",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "eab98578-8f6c-41a7-b23a-04cea8e8f9b2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ccf4ebed-0538-474a-9bec-961b075477d8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b7ddadf9-6746-4172-a6f9-207801771238",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "304811b6-17fb-47e1-922e-edb2a85378c3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9555ecbe-6ea3-49a5-bbd4-a69c9422a7db",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "280242c3-364e-4523-8718-c93b16098290",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b75a440c-0ec9-4026-a3b6-cf2f7457ed30",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "34df0203-744d-4cf4-9177-21b6b856eb2e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "d36ee42c-9046-431c-9105-5e6399e101d4",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FEDLOAN SERVICING",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2016-08-30T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 340000,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 450000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FEDLOAN SERVICING",
          "institution_address_line_2": "POB 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "315e57df-7b75-4f4c-9a61-bf7f1dec222a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "30b617f6-374a-4796-9d20-46ce8c8ce6c2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a07bd83c-e117-48ee-be36-32f2c25188c5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "29d8a95b-82e6-44d0-9e12-6ed2c8e363eb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "efac6fdd-caa1-4851-8653-b815754ec6c7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b0fe61d6-9cac-4778-acaf-d4e7cad77c33",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "914becec-7926-40b5-8361-ed5f40d2ce5e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ac4dab19-62d4-4b4e-bc2b-11277817401f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "20c19550-1953-4679-8bb8-54c1a6544df2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "94d741d4-bae3-44eb-a21a-3680a6af1020",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9c63c504-8f38-4d5a-b3c6-2da65a5fb80e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "32f553d8-5196-464a-af14-d174b53274c3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4ca5591e-62bf-4c81-8faa-09654b84a1a4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "148d1fc5-5a5c-4b94-b66d-cc4674990c62",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6ed8bcce-4387-4578-bbe8-b14a72b9bd46",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7855e050-8d68-426d-844b-802ef0797f4b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "800290be-eb92-4f01-adbd-8933a0f61941",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8a0cfcee-8ee7-4e93-b12d-e66a617efa04",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1a48a52c-dfde-447f-a2b1-38c4bc041eff",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "851e826f-4250-4118-81d8-d15791465d2f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "82603274-c579-42d3-8311-de3f3a7b7fbd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f8ed7872-e3bd-4f38-8030-e0d9818c7b61",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "abb731a8-4a77-42bc-a0a4-90ff047595bd",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "SYNCB/PPC",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2016-04-26T04:00:00.000Z",
          "term": null,
          "open_balance_cents": null,
          "balance_date_reported": "2021-07-01T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 32200,
          "minimum_monthly_payment_cents": 0,
          "monthly_payment_cents": 0,
          "last_payment_date": "2019-04-26T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "SYNCB/PPC",
          "institution_address_line_2": "PO BOX 965005",
          "institution_city": "ORLANDO",
          "institution_state": "FL",
          "institution_zipcode": "32896",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "e005717e-baf0-44c3-b159-644e984ea97d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "61f9e945-2642-4c7c-8acf-597f3016a73b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "dbe6fa7c-9c93-4574-809b-19a8fbe207d4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "656b0604-d529-4583-88a5-3f79efa7eabd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "88ccc7eb-0399-4436-9f0e-319ee99635e2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8e0feb0e-3839-44e9-b1a4-e3fa77ca6509",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "463da332-766c-4dce-805a-e87efd89f56e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3335b52a-2968-47e6-9f58-7016030caab0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cd050a2d-1885-4882-acea-22fb2b6427f1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b13e65a3-7f54-4466-8756-21172b3a5c35",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7c2e5299-10bf-4460-a12e-3c86cf71f5fe",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8d4b12e2-19ee-4eb0-90d2-f5c6f2684cd3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "820fc1c7-650a-4416-97be-f9eca1c5f3f3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fd6f764a-5f54-441b-b750-73f5221b7b78",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bcc5cc34-3010-4bb9-a6ac-9b3d0a5387b8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c376b594-3ed0-47f6-8a21-5c597d848485",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4cbc67c0-38bf-48ee-a16c-88a4f758d5a1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a346321f-a9c2-4e92-b655-0db6ce975c09",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "89e0cd4a-9d8b-4fcc-9f99-52af6a0c04ff",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5d158d50-17f8-498a-bcae-791db1646d20",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "30121bcf-3b04-47d6-8f78-a31d42f3b158",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 6,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4b779bc8-7c32-4bff-8af7-fd1be2dc4882",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8ceed4d0-b374-40e6-b940-cd8008a20e35",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8050ac90-6066-4947-b8bc-aba7f7fdbf0e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0bc40955-0c04-424f-b8ba-1707f01658db",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c3b3769a-342b-421d-bc31-47bcee7aff80",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "97f61c4f-ce0a-4563-80e5-cb1266c43355",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FEDLOAN SERVICING",
          "bureau": "TRANSUNION",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2018-09-17T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 291000,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 375000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "Current",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FEDLOAN SERVICING",
          "institution_address_line_2": "POB 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "fad549f7-c53d-4a42-b1d5-a7bb40a31d2c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9a43ff30-dd14-4f84-9bb1-65dfc0ea8285",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7267fb7b-a6b8-4acf-a939-5c33bb3cac5c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7afb2b8c-878d-43fa-830b-8649072a0c62",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e8637785-1447-4336-82ca-7e9b29ad7631",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "37df3e16-84e5-4ddf-9a1f-0d9c55e0fd78",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a1fc25a3-da2c-414c-a511-7573bfa92595",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "697a15c4-7fdd-418e-a330-f12c3d121380",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "248e7b6d-ed77-4afc-8977-bfa11b751118",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d480486f-095a-41d6-8bcf-18e41f9a91f1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b3213444-21c7-40e0-a730-753944518f1a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "6b678a55-20c9-4d48-ac45-d83e2cd6aeda",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "339e7e6e-2ecf-40ca-9683-ede415187402",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2ac8fc0b-9782-4f18-88bf-a0f356b10c97",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 3,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "153ccaae-d522-4d51-9766-f080dc43f5a4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "dad41983-d017-4ba5-9d43-bf8678d80d08",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d57f463c-99fc-4016-b54c-db96cdaef9e1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e3c16565-29b8-4a46-b8a8-e90aaf136e15",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "79d1f510-088a-44fc-b8c6-ed31487e0186",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "eb073e4c-1957-41d2-a109-6afda040d349",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "40350dc6-218e-4f0f-9258-8e947e1ae1d8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0d242d04-429c-4123-a4ea-06df3f53af0c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d7146fb3-57ef-4df5-b336-fb45b3dcf702",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e1ee1fff-f99d-44b5-bce0-d2a32d527e09",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f8c38463-2d8f-42cb-9954-c716b129431b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "77370384-822f-437e-89fa-57db0e8c2c3f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3231fb8d-37ad-4651-8d56-f2e32d234bb8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fee14722-c7c0-4fb0-8e5d-0727bcf425fe",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "41f25e2b-f132-4b83-b6f9-a430a2d0fb9a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "afac3937-51aa-4dff-8c75-cc8d4c5b28b8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6061fb39-e2d9-4d24-8e76-ada4e644826e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3c383747-fb3c-49e4-b8e7-fa583250d740",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "07d5b96d-f905-4a7d-8439-d95fecfa3e16",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FED LOAN SERVICING",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2015-11-09T05:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 263300,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 350000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FED LOAN SERVICING",
          "institution_address_line_2": "PO BOX 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "869a35a4-4605-44c5-aab3-f1f56764b556",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2015,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5a3f922b-cf5a-409c-b076-5d7c0e213b58",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2015,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4e8beae6-187b-4814-b6b8-aaf6f2b903ee",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f6c48201-181e-4735-aaac-44433d927a30",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "427d4683-fcea-42f3-9b1b-3059256794ea",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 10,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "163107eb-bea7-45dc-8ff7-5bc635783616",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 9,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7cca2ee0-44cb-471d-bd2a-a809b6029202",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 8,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "bd81891a-76c7-423f-8589-1af5408c1f1b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 7,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f30e5026-5567-4e66-9f04-801422650441",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 6,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4b074572-787a-410d-a19f-25d5360b3c42",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 5,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e402bb83-2f00-4fb5-8135-f9c1bb407cd9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d6748c55-3fc3-4b52-bfcc-e1d14e6807e9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a7ffacf5-bd0f-49e3-9982-6bf51652e00d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d2f7ca2f-9460-4cb0-b497-abb094aae664",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e5f9cf2d-d452-4084-8019-fd90d5ae2add",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "19c7434d-721e-4e43-ba09-05e37789cc25",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "466fca1a-9817-4a33-b314-a5a395f6102d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 10,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "c145f666-ac94-45a9-af06-d2a05bc53fe8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 9,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5b708076-eaee-4d2b-ba6b-7e3e6144c385",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 8,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7647079d-76f3-4b33-ba8e-c948043a4d6b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 7,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "046f0f0e-4137-4eed-b8eb-cc4e5d26b93d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a07a20b9-e8d3-4f3d-a33f-75d8debd8807",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1454db6c-a1ff-44e6-8e60-bbaf20f7da18",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1001b69b-9f95-4041-a1d8-c3e1b2b6b31e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a2c0cb97-6376-4290-a7d2-dfb7fcd93cd2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "eb82d4a2-31df-4f70-96a7-63f674145e2c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b1491a8a-9080-4b37-b4ee-8137bc7604a7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "203af616-f1a1-4bfa-98de-1ca93572f92a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9773f423-74fc-4fba-ad26-7830d5f88d72",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 10,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e3c7bac2-da20-462d-82db-1dcac87e46b1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 9,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "25e8f070-907a-4283-a084-4f7ed9c9778f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 8,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4c54137d-5d63-4677-ad10-f3315c7fa560",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 7,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "690ebcde-4ba2-4bbf-9ffe-8b64b54499b6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 6,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "15769d22-d0c0-461a-a626-f57f6bec4de8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 5,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3cb4a853-b711-445e-8887-4d7ca930f4f1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5a6bd0ac-7df5-4eb2-b552-830a2cca2302",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "aa145c1e-b484-4659-90a2-1f6f44451bc3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3b38b9e2-4b6f-438c-aec1-52faa8b55891",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "0e30a31e-f820-4f5d-a69e-847c5f529386",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d69f314e-f5cd-4b6b-aab2-950daaf54b88",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e83ee050-6638-4364-a110-1090d917da0a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "85404761-a58d-4bc3-93c9-95cb5a0a3a10",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "adbc5e39-b25c-410c-8ed7-55d7b86f9b46",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "41b7f338-eda4-42b8-a196-b3a670ea6e45",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "34fd0a5c-5955-4ebf-9792-dc620ee81110",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ba2e0b6c-8682-4520-94ac-d33c2bb74632",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 5,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4fa5819f-833f-42b0-84e4-1b97f3c69e99",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e7f9b3f7-b3ee-4d80-843c-b78fb14edbb3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "731c8a77-15a9-4285-a5a0-ad3fabfaa840",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "396ff796-cf5c-4a34-96ee-1cfdbc130a62",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "79a8789e-eca6-4f22-a586-4685c387d545",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0f6b7342-c62d-4d40-be85-ef11a00c70bb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "50e1dc91-2990-4ade-8b50-0905f7e85290",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7b928876-a9e7-41a6-9990-730135186526",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "33d433ba-04df-41e6-b091-9321a6d76105",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a57cd5b5-a5d2-4103-a2a7-0805441e800a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b550056e-af2f-4d59-969b-dffd49cb9207",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "42c64746-f80a-439b-84ae-787d632bdb9b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "304832c9-fd30-420b-9ada-ae117b1a6d02",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5a632233-6e0d-42a0-b42e-bcfa5ac2c7ba",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8355ec5d-4709-4763-bb62-9069c61bca2e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "11afa0ba-ca1c-4608-a1d0-f82226b68962",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b5752478-9467-4438-a54a-7538f96ffaf7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fb6c7657-467f-4521-bd1e-653b96313c55",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "24d51dbe-0125-4315-ab78-9c1a83a92e6b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9aeb4966-12b8-499f-bd73-68419f0c8dd1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "3fcc47cc-da4a-4539-adc6-e3e6878ac731",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FED LOAN SERVICING",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2016-08-30T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 165900,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 200000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FED LOAN SERVICING",
          "institution_address_line_2": "PO BOX 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "30c2e061-ace4-46ba-a4b7-be99bba4e2e6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3a73b51d-31c4-4978-a1ed-9b18734c3977",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 11,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "29295197-1765-4a85-abba-4b487193b6d1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 10,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3b10fd83-423c-40cc-a165-57f9b995b508",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 9,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ee0488dc-70a1-41a8-a0e5-ca71d03bfd4a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 8,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "239b5677-e4b8-442b-a7c5-a93503b9d21a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 12,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9475b4b4-41f5-4cb8-afc3-08412751f2e4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 11,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2234bebf-03a0-44a7-8bb5-61f5d97c45d7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 10,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "56cd660b-ad59-4f96-9a48-cdb2a76db7b0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 9,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a857064c-c15a-4bf9-a949-43474f2ae9f2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 8,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5bff7a1d-7bb1-4078-ade0-86e441efd7f1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 7,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ea3c98d0-e34c-4fce-9112-ea10aec40f57",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "62f851b0-2d25-46a2-afd0-f950670e756f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a86184d5-cf75-4f7c-9da9-586859a8121d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a80c755e-3ecb-437f-b2ce-f8ef37ea3336",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f285a570-a7df-4a41-9a7c-5abf403d1538",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2d5aa032-2579-4ae9-b75b-3a5e2ccd082e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2f59d0e5-547f-452d-923a-217f23cf1a71",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 12,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "466c4a13-5582-4461-bec7-51ac63f952ed",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 11,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "26a04b75-61df-4411-9190-0b840939f04c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 10,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3903fd17-64cc-444f-b04b-af28c0b1905a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 9,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b16da20c-5af4-4c6a-b39e-f77192dafb16",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 8,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "cf9a4ca3-594d-4af2-8e2f-acf37f84e205",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 7,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4b6572b8-e7d6-4d30-8720-a8393bc7a5e9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 6,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "41957ea8-d824-433f-8a02-5e46bead20e0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 5,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5a42d76f-4c32-4420-9c5b-e795d283de32",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 4,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f8243256-078f-484e-9c64-9c809842b750",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 3,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ec468bdb-8563-4535-8bcd-95eadb3da30a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 2,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3a0534fc-d3b9-4914-b117-3395af769085",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 1,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "c8ab49a4-c9c2-4f7e-b750-e9c1c70b2690",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "25a5f7da-c89f-4c3b-af54-e8065130166c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2ff538ba-259c-48d2-a8ad-29d6712ca554",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "84650f74-efe0-4dab-868c-03dda93d6fe6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "de5ce3e0-cfb7-4498-9b5b-b2c2fd090923",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "041a7e21-42ae-4463-bcbd-8aa5b49387ff",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "700073f1-7d9a-499a-ab55-cd1df9adc85e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9ca543ac-d266-4a28-8559-110dfff15097",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 5,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d3241b7a-90f3-4e1e-86dd-e557028f803e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 4,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b034de0b-834b-4c65-8ba2-7382abfeff82",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 3,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "504c20c8-4d84-4f4e-9917-0a2c42bb678a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 2,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a915f53e-fdb6-4c16-9e41-7c1634fcf95e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 1,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5dbfa03a-0ebc-4cf1-8259-fb75e29bc0f5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "93770cc8-c229-4dfe-a4f5-0a8e101052fc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ec7d30ee-733f-4d01-8dba-b28f93464a46",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f4faeb60-e54d-4fff-994a-4269e02db5eb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c59e4a3e-2931-4efb-a7b7-92cb81fa2d08",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c663e332-2c9f-4998-a2c4-d9b6cca6e6dd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "996781cb-3200-400f-aa2c-0fca20755080",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ad1219f8-d7ab-419c-8073-848e60a79638",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0e984a4f-f190-4aec-9ac8-38f8b173a82e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bbb2b2c8-b7f7-44c7-b2b6-21dbce3f1363",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4a2c9576-2d0c-4926-9561-2f258b1c055c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "79a186b7-501f-4241-9525-ab5a9739f37f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "08e5c4d3-83dc-402e-9243-d600615af604",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fe0f658e-9512-4ef3-b8bb-a6f752dd51eb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ee5b4659-93a3-4d18-bc07-e3995c549f91",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ba08241e-20fe-4bb9-8acb-ebd121e8b29b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "a5edebea-f3e3-4133-8f9d-64818ee1f428",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "CAPITAL ONE BANK USA",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2016-12-09T05:00:00.000Z",
          "term": null,
          "open_balance_cents": 86200,
          "balance_date_reported": "2021-06-07T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 350000,
          "minimum_monthly_payment_cents": 2500,
          "monthly_payment_cents": 2500,
          "last_payment_date": "2021-06-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 2,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "CAPITAL ONE BANK USA",
          "institution_address_line_2": "PO BOX 31293",
          "institution_city": "SALT LAKE CITY",
          "institution_state": "UT",
          "institution_zipcode": "84131-1293",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "3b6d8002-238e-4760-9fed-71ea83714219",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ef8eb584-3fad-4011-9e5c-3ab669a655d1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 12,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e2697739-9a47-4c13-8e7f-9d14060fa176",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 11,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b1d4f526-6061-403d-be40-17f40a5c5b01",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 10,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f57cb121-925f-40d1-bfe6-bbc99b596a70",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 9,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e7e616d6-e4b0-45f2-ab9b-f8cd88be3899",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 8,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "96f1773d-6d17-48f0-8cc2-7dbbb2317913",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 7,
              "year": 2017,
              "status": "NOT_CURRENT"
            },
            {
              "account_payment_history_id": "60952c5a-b479-4f03-bce4-a3618d3fdf18",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "56f168b4-1794-4dce-9745-902a857aab55",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "0a3914d9-9c25-4fca-b21f-664121b69e6d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "70989afe-8f78-4c7a-9e30-f4c332e6e388",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5517cd19-5a75-4ee5-b9c4-5c166f12738e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "61465f8f-d637-437f-8a17-359ac61d97e1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "41a536f7-da09-435c-aa1d-917121927daa",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "61a11aab-c6fc-47b0-a1ca-763a70b63044",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0eac6041-112b-4e78-aa6d-bc4c8658aa75",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0624500d-8f70-4310-abcc-4992e9f991f8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5626a555-218c-495b-9768-e18fad0ad6dc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 8,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f12ea320-af13-4a8f-9878-b2944f15faf6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 7,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ce5c4f58-e7f1-4a0a-a2af-b836c7ff7832",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 6,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a852f30c-2268-4d99-a77a-1a17b1b940fc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 5,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d185c9c3-90db-461c-8764-9d2e38d55800",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 4,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9ed9f187-0653-464e-8c10-959566344001",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 3,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0a9c1925-9a42-4cba-8eb9-f4b1177bfd0b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 2,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b0a5bcd8-d948-4cc3-94b9-1141258be1f4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 1,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9a29f3e4-937f-4201-bd3f-a68eed3205a2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3e88ff38-126c-4ef6-8453-c8ebe48ad624",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5ea39adb-7ce7-482d-a04a-27cdf8fca623",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "462153fd-4d57-482f-be4c-855997569862",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ebdbd2eb-b7f2-47ec-90f1-38a0608d0cf6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b6ae85c2-bce9-4d36-b8b1-5db421ce8607",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b306a196-3e72-4bb4-9d8f-25d8310c477d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "aad55d79-5e48-4213-8091-432994ec33da",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fd0994b7-0762-461e-bab6-42a84af68f81",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ff30511c-1277-4366-851f-2a310e1b3dce",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 3,
              "year": 2019,
              "status": "NOT_CURRENT"
            },
            {
              "account_payment_history_id": "2ade9f2a-4a17-4a77-8a9a-abbde9aa4e2c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f9787a0b-bacc-431f-9a4e-c823774da58a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3027058c-57e1-4e9f-83a1-57af2c9125c8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "62e86e7c-a750-44bb-adfe-932f2e0a91b7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4b4e741e-0c08-4803-9435-cb8438ecb425",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5d4aa2ec-04d3-4786-9561-5894d00f7019",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1d556c3f-22e1-4426-87d8-a236ea870052",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7bf23685-0674-411a-9785-1c38f524dd99",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f7b9b4da-db50-4c79-8817-6ba91fd04f49",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f0f9b6a4-23c2-47c6-aef0-cd52f061ef35",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "235f28bb-b7d1-4e94-9cfb-90338d02ae9a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "30c634aa-469d-4293-a59b-683599d822a6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e806ec46-2c4b-4ff5-bf11-5068787b3963",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c30a1b7c-74f2-49e1-a493-6a89fdc823f8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "956d9fe1-344d-43ad-be52-dd56a31e6959",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5aa1cd7b-dd97-4150-9b6f-40608940e17f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "edf65cd3-6b78-4f4a-824d-a8a656da4332",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "baf14f95-1b24-46cd-96cf-5b5ce14c1060",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3be79753-d205-4e93-afec-7a6da9389231",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "eae8865b-bff1-44d9-bc77-664b43d8107d",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FED LOAN SERVICING",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2016-08-30T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 340000,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 450000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FED LOAN SERVICING",
          "institution_address_line_2": "PO BOX 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "d1bba03c-eebd-4a4d-92b2-422708631067",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "344e4465-9af6-407f-baa3-774a35e5e854",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 11,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "102d9b7e-14cc-45f2-a1e1-c227472c066b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 10,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f2dc0267-a833-45d1-9af1-87d3f72281b2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 9,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f2249fd1-8de1-4187-9971-f79c3a498333",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 8,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e74b78ab-cd76-4851-9b7f-d9a0155b640d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 12,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "daac2171-90e4-4b13-903a-a260e72959d5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 11,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9a3b66df-b773-4f68-bde5-b9e54cb0b526",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 10,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7c895d8e-32f8-49fd-8e4e-d46a5a4debde",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 9,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b5fb733a-dbcd-4bbc-a364-010a794d07e1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 8,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "af6d1009-98bf-4d85-bd96-366705ee2fba",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 7,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "80c7e40f-6fe9-41b4-a994-eede87b5debe",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1debac23-0352-4929-8870-aeab06b6690e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b32c6dcd-c307-4e5f-97c5-4571fb5df068",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "801cd293-2396-49f0-ba6a-6f71e957905a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "49e791aa-c60f-4d1f-b2eb-5cd240e50198",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "036bd6ee-40c9-4c44-8f07-98626ac3d845",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "dba7ee69-7e2c-4914-979c-ce74315c74d6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 12,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "403f3fb9-480f-40b3-b123-9f39fd4fdfc4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 11,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "23037b58-1544-47e8-9627-fc25af84d1ea",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 10,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "0090a813-9f71-47a3-8a4c-e823f323fb1b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 9,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "44937460-ef8e-48b3-a1b6-88da131c5ef1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 8,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "8e27b0f0-f777-4f48-b7f8-3d640bb11f42",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 7,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3d16f049-4682-41a4-891e-2e051e149b27",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 6,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "6b24ac87-6404-4d1c-bebb-c7283800d18f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 5,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "df3ece68-2a70-4894-ac28-9cd8f253f153",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 4,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "823e0e74-9936-4f80-90f7-d3b6b9173116",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 3,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3467f8fc-4f43-4904-93b7-3bb47af81a54",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 2,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "652693a0-d3d7-49db-92e7-d40c1e5aa425",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 1,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "770c46de-bfc6-44ee-9daa-e313ed45ce35",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3ce578a4-fe14-4835-a9e6-a27d41fa56ee",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "aeccb08e-4dd2-4baa-83fb-a86480431448",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "25fb0f4d-261d-4e89-9ffb-77f481b9ef59",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2e38c778-dbcc-4c48-b540-51bc80a31e74",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "92509ad2-c08a-4708-a04a-dd5a9fdceeb6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f596390b-37a5-4dbf-a51a-336306e7b086",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d6d09f47-4ee5-48a5-a46f-82cb4cafea92",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 5,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "48e1473d-69f8-4e90-a03f-4205ea771124",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 4,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "c7210717-e679-4ebe-92e8-cbf79e8699a3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 3,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "561e4276-c3c9-45d2-b70b-3a52bfb670ea",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 2,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "82b28e28-a310-4708-b012-9f93f21f13a7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 1,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "899298d4-47d4-4076-9602-fa401fa8d9b4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e37d7865-930a-4f0d-93f8-b817c190bc5d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4ef16e18-76d6-4ea2-b2ef-9949759b37f4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a8022c4b-0b4c-4c23-9df5-13da4b3dee10",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7a323c56-1077-4446-8bba-b77971268286",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "52cf00cf-3632-448e-aa85-39f3123a5785",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ba9e6502-dfb2-4c90-8bd0-9e70c4592562",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9a43a484-e183-4213-8057-4637fb3f3be0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4a165062-0217-4cd1-a912-3da8e45df938",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fad59842-f07e-4f9b-bc9a-08e8232dca08",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d227a215-5f53-436d-8a6d-afd8fa9ab9ec",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0c686bb7-ab92-438e-bcb6-7681f72f5aa6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "de93bdd0-cde2-4f2c-aa10-d8a3036e0c9f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f7d158df-5673-4e86-aa75-cf02593f2be9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "45abb19e-79c0-452c-b7cc-ef7dbe2d9042",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0799f211-3418-4f3e-9bc1-1d459980ef70",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "39ba3828-0921-4f29-9694-759d8203420c",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FED LOAN SERVICING",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2018-09-17T04:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 291000,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 375000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FED LOAN SERVICING",
          "institution_address_line_2": "PO BOX 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "260a3056-a6f6-4174-bdc7-b3efaa870596",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f5e3b95d-a2aa-4aba-97f7-b8987814f55d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b8c7b807-c63e-423f-a36d-8748603f369a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "22c40f07-4cfb-4503-8c42-457b31f28ea9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "63f6d428-229d-4359-8240-bb1058997194",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3760fade-0f0c-4a2e-9840-764e1ac54d14",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2da57746-6f5f-40e2-9beb-e10d5691b4b4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c3091f63-ce89-46b5-a3ce-83fcb4fd724b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d993b004-7f64-48e4-861e-5b55e7342fb2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d45edeca-f7c0-4c46-88d8-e2bbc634fce2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2b5f9923-2e3e-4807-8c65-97baf87eb284",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "787d66a1-b482-41a0-ae9a-404a18536145",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "dca869a3-9eea-4c07-8c59-6e94d99ac952",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1783997a-be1b-4da0-8a71-44edd3412945",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 3,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cb8ca4cf-12d4-4447-80c5-e5f4d08209f8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "aede6ca2-60db-4c25-8287-34ddd8b926db",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "837ec6c7-8a5d-49b7-9cc6-637568eb9c80",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9a756c76-5cdf-494a-9863-fa87c3d5a380",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9e7f0e2d-18a7-4a89-ac5c-f18afb0d4704",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2bf9d0bb-5cff-4897-9d93-eb0736e03423",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "31b059cb-3743-4993-9d19-1d33e43e8769",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1722e2f9-2ba3-481f-83e6-93bffcf8a413",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a2f91378-603b-46b0-8910-4e6d902ba8da",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2ece11f5-b5ae-44aa-a888-39b188b8cc8b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7ebb1d17-9918-46d7-ab96-95c20e098d9c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3a5091ea-1309-4a66-885e-ff4f02f2f1d0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4279d5d0-c1f9-4ab1-a39a-ce21c7c02b7a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4ea317da-3315-41b7-b40d-89aa80bde51c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e953bde4-e0a2-4ca6-8cfa-1dc166104c35",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b9b20422-795d-4e3c-86ab-730b475a483d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e3e02cdb-27c3-4c51-8b36-9ccba48174a1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "0454505c-79f2-4bfc-9a3e-89b7c5c5647f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "e631361b-be12-44eb-8976-eac4ba724f2e",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "FED LOAN SERVICING",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "STUDENT_LOAN",
          "date_opened": "2015-11-09T05:00:00.000Z",
          "term": "120 months (10 years)",
          "open_balance_cents": 173100,
          "balance_date_reported": "2021-05-31T04:00:00.000Z",
          "highest_balance_cents": 200000,
          "credit_limit_cents": null,
          "minimum_monthly_payment_cents": null,
          "monthly_payment_cents": 0,
          "last_payment_date": "2021-05-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "FED LOAN SERVICING",
          "institution_address_line_2": "PO BOX 60610",
          "institution_city": "HARRISBURG",
          "institution_state": "PA",
          "institution_zipcode": "17106",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "19ff3061-6013-44e8-857c-c2be7e7d3653",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2015,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a58bbe1f-64b3-44fb-95a2-4c3cd74ddf1f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2015,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "fe31a87e-c4e3-4a28-aed9-8e5d887dad40",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "6a755366-bef9-4080-a6a7-b4e7472a68de",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b050cdbb-ec49-443d-b2a1-9e03ac83e72d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 10,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "bf669e12-8da1-4f96-acf6-6961880bb505",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 9,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ca0212d2-facc-415d-97b6-5ded8f6a3ae5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 8,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a8609fa3-8016-4759-8140-81f6563800e5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 7,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d4217936-db18-403f-b620-12443e4a10a9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 6,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e0a4ebe0-d9ea-476f-b5c1-4904ab22b020",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 5,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a51339e3-15d7-4973-86b2-da2434046a54",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7ee8600f-abf6-46a9-9a3f-39d6b322fee9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e56bd23e-abcf-4c79-83bf-6df499e40457",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d3d4507c-33ed-4c53-b4f1-68710cc720be",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "29dc3746-0bc1-406f-96b3-636553f54da1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5f485583-fcab-49c0-998e-b0575910f77a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "74163225-325a-4ba9-b387-0b0cbbc30b75",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 10,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e20484cb-7aa6-4698-8901-96dfb0c8520d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 9,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b6661849-408a-48be-9292-bf1fd6d0966e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 8,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "dc35eed0-37fd-4dea-9e52-198df16cf800",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 7,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "169477af-9ec4-4fc9-afc6-399d8e376df9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7c9ad156-d5ea-4ba0-92b2-e67ba7f70522",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5e03b501-d194-4741-9c47-1677858cd4c6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "0f7d8c17-b379-493a-9814-d66ec1332fba",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "16dbe758-86fa-47f5-ac83-572c0ffc59a2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9a266c99-196c-466c-99f0-0c14a2d51abf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1f2e9d26-e255-401c-9351-98db9133493a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5d2ae421-db96-4f68-96dc-344811042c0f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a60ad0b1-08ab-4dba-b33e-f57b272f3ef8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 10,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "c9fa3804-a9f8-4503-868b-92c4a58c6f19",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 9,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "31e800cf-fd5b-4152-a8c6-a61400e340a9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 8,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "646da9ab-23e5-49fb-9361-6668c4b4fdbb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 7,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3bb9ee06-aea4-4e0e-9ab8-f7cd3cdf530e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 6,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b224048c-2295-4b1a-9937-32a09920858e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 5,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "3cca14e3-a31e-435c-b314-7bacba0b0b19",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "c0bc4ba5-2402-4663-b04b-1c4db9c7a6cc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b5a088bc-6592-46e8-9a44-4de8ca92541f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "e08486fb-7908-4b54-b4bc-90171a000b28",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "02a8b54c-413e-4e9a-8704-1897892c8636",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f35fdd54-7636-4126-b945-147be98ecbad",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2315ae90-f6ac-4b01-9273-d6b23b3f7dba",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3e0e0989-781b-4d55-b646-d844af0dc221",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b769451a-1261-4d46-9e4b-3a58ee196664",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4dddf594-bee2-48f5-b7d8-a5cd5f2e0974",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cefa365b-ffdb-4745-b44c-a73aaa9a2d01",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 6,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "075d74f7-29c9-48da-b4fd-00eea99e59a5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 5,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "fa4217a8-9583-434f-9ff4-187f3e4ac6d6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "84881ebd-6194-44cc-8cdb-5ab939d08dde",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "571dcd51-fd28-4d12-b2d5-f291f2e6092d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "fb7be4b6-f3ae-4b21-8828-226677900e7a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b5ee245b-63a4-4bb5-86e6-9095ce97a420",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3d5943bc-8b3e-4e53-9e54-0c9c37f39cd0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "e4c02799-2143-44f4-9b3b-0f62d9ed3626",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "48e412c4-43fd-457e-917f-c8f87993b09c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "31f510d7-8da0-45cb-8d1f-0b0e9d7cf855",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cc4ff56f-184c-4bdd-8334-6030b140f396",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "df12deac-c2d8-43b8-9d23-02f5ff9486bf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b5d26ae0-f14c-4a2a-aeb8-e2665d46e6f3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d7716514-23b6-4ed3-9ba6-8470724b1db7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cd158704-7c96-4186-954a-1c7a1a7dcd33",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "39facd04-c46b-465c-b2d6-c132c0d45b2b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "02779425-d2ff-4bce-ae31-42a9b9eba23e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d5aaa6e0-a0f2-4cdb-97d4-3da82ec9cbd7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8c8cbf15-0abb-48f6-a080-4b4e80d81bfb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a3e99bcc-52fc-43a2-8544-ee62b6c9225f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7da8e845-9124-4c70-8410-594e1a924063",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "2ef9901c-bd6b-4bef-b51a-53bccd4d8293",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "CAPITAL ONE BANK USA",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2017-09-05T04:00:00.000Z",
          "term": null,
          "open_balance_cents": 109000,
          "balance_date_reported": "2021-06-19T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 1500000,
          "minimum_monthly_payment_cents": 2500,
          "monthly_payment_cents": 2500,
          "last_payment_date": "2021-06-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "CAPITAL ONE BANK USA",
          "institution_address_line_2": "PO BOX 31293",
          "institution_city": "SALT LAKE CITY",
          "institution_state": "UT",
          "institution_zipcode": "84131-1293",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "e3adec8f-4172-4ad6-909a-0d7bd8e5e114",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 12,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d112a7ad-05c2-458a-8fec-8d39da4cb094",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 11,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f899c775-191b-4fce-97e5-c3699590bfa5",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 10,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cae2abec-ec4b-40d3-92e1-7088c031acc2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 9,
              "year": 2017,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3231ec3d-20b2-47b6-8d44-7ead70ce391b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 12,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f0d9f4b0-461b-4824-bfd0-57abdaf245db",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 11,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5074e464-3d28-40dd-aadf-0538a982c3a7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 10,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a45bca0e-a92e-4ea1-b76c-24590e893169",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 9,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c9872c85-b025-4161-9776-e10ad577efe7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 8,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "45954212-2244-4e84-8c1c-998b494e32f9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 7,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "aee82968-e2ad-413b-ba7e-f4592766ecae",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 6,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2d73040c-7faa-4388-b1e8-5c4347bf5659",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 5,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5b92f180-da05-41d8-84af-045aee3efa46",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 4,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f6c505a6-6ed8-4411-8cfb-bed62bafd6bc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 3,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "29f12b5f-2b76-4f1a-a136-ff7fdd5faccf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 2,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cd5578d7-fede-4fd4-9227-afa4ce227af6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 1,
              "year": 2018,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1bc843df-d31f-48d2-b8a7-5f86b6969f99",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "586c3175-baf5-4e00-afe9-7d1f444ac21f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "364743bc-934b-4d0c-81b2-7733be5b2bde",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9352e07d-e996-4a64-ad82-4526f2683e05",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "bc5b59f9-e2a8-4017-a81c-d1920df90310",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5974171f-80df-44e6-bfaa-9259846c2731",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "43f1bcde-6405-4149-8044-1212e7df7d96",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "47550d77-f299-447e-9c5c-d4b54765a0e0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fc5b4098-16cf-4c25-8f32-5ca26e4aadc0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 4,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "cf0a0858-3355-4fc7-bd54-1e6a8446814e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 3,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "54e7afc7-0c29-4a06-a943-a34f0dfdbc95",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 2,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5a4723b9-eb0f-4ab0-8d8e-391c0a87ccd4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 1,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4bc20d8a-d00e-45c3-8800-9a80150b4f87",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "050712fb-82cf-4b5e-a2b3-7156b8995383",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "4720ceac-b330-42c6-9383-d625d393f7e4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8dac1a95-5b1e-4193-bb13-62e19926af41",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ae6822ae-26f0-4739-9db8-f12f4495bae8",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a5747af3-410c-4f44-83da-d4271ab8dbc9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "213542aa-f74c-4841-a9ee-26f3e9af68da",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "9deb3432-8859-46cc-98bd-ea7cb2091c27",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8c738b08-2a85-4424-804c-1adc5e5caae9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "1d7d3447-5f3d-407f-9842-78e7250fc66e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "683171ff-527d-4b79-bca2-fa6c1137c523",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "45578e46-0757-40c5-b2af-03e983a4ff1e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "6700d48a-bb6b-4585-ae86-7f5866ae4cbd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c219641e-f9d9-4753-93ec-c9dbc6b736ad",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "fb2adebf-4821-4b86-bbaa-e033519165d6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "498cdad6-2929-4529-8822-b816ae656b76",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "c507cffe-bd73-4c83-8041-a09abf19ca0f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "49005f32-ac7d-4f1b-ae58-4528858e4f12",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        },
        {
          "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "name": "SYNCB/PPC",
          "bureau": "EQUIFAX",
          "status": "Open",
          "type": "CREDIT_CARD",
          "date_opened": "2016-04-26T04:00:00.000Z",
          "term": null,
          "open_balance_cents": 0,
          "balance_date_reported": "2021-07-01T04:00:00.000Z",
          "highest_balance_cents": null,
          "credit_limit_cents": 32200,
          "minimum_monthly_payment_cents": 0,
          "monthly_payment_cents": 0,
          "last_payment_date": "2019-04-01T04:00:00.000Z",
          "worst_payment_status": "--",
          "remarks": null,
          "times_30_days_late": 0,
          "times_60_days_late": 0,
          "times_90_days_late": 0,
          "institution_address_line_1": "SYNCB/PPC",
          "institution_address_line_2": "PO BOX 965005",
          "institution_city": "ORLANDO",
          "institution_state": "FL",
          "institution_zipcode": "32896",
          "institution_country": "USA",
          "account_payment_histories": [
            {
              "account_payment_history_id": "483ece23-7ddb-45f5-9eed-0feb389d5ffd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 12,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f8c5e9af-24e5-4c9d-8f98-e12b278657a9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 11,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "49195625-a2c2-4f10-82ce-e42ae039bf66",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 10,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "edf8e810-8987-4f53-add9-294942257024",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 9,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ca409e22-d7a7-4811-b3c6-5ef34d06a6bf",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 8,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5f2e5599-ee71-40ae-bfa4-f4d141f6d264",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 7,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a11f473b-88f9-4b26-bfca-3f7fedbd9cfd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "25bb2843-de14-48fb-b617-bfa08493b99f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "5b8b62ad-aa51-43b9-b3e1-9db91e0105cd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2016,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "996aac2f-6376-4c8d-8a10-01643f604051",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 12,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2f86c3f9-5e22-402b-94c8-6935d89466e1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 11,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "41e798a2-68f0-49d8-b48c-aa32e6b93700",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 10,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a48e9600-0210-4ada-8945-cbcc011f9cff",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 9,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "91fca0ed-b7c0-4bf4-b0e4-114e5c91b586",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 8,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4bad6127-20ea-4a74-a736-a0ab00c635f2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 7,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1a67319a-3a28-4add-8524-ebc0340ea590",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9c4a36c9-045c-4eba-947a-18d56eb010c0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "f12d179e-c19d-4095-931c-9ad3543b0c05",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "9676d904-be7c-4675-81ad-af7ae9adbddb",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 3,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "a5e2b8e2-29b8-4273-9ebd-8f02548a66b9",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 2,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "45ea20fe-1da9-47a9-9f1d-d1e51126331a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 1,
              "year": 2017,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "396d752c-009e-4f35-aaba-d5bedd10c5d0",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 12,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2f001ae6-e9cb-46bc-9509-2e81d8d86141",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 11,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "b9702b03-2771-438e-a210-c3cfca1b8209",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 10,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2a309bcc-a0be-4b3d-9398-268bfcad30c3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 9,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2058fa44-d425-48db-bd00-11b34e5d2df4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 8,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4206313f-ba8b-4c10-9dac-08261ae7d048",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 7,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "187aa3b4-ffc7-4508-a7aa-961f5a0fc0b2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "ef657249-140d-4300-8bd1-76a912d5dbc4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "56c50fc9-1306-4362-b3c8-a2319e54d0ea",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "4cff57e5-81ae-414a-b58f-fc9b7f89946c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 3,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "2e609aa5-82fb-4462-8932-5d40a6b703c7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 2,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "aa871077-a9e7-420c-872e-dc847793f591",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 1,
              "year": 2018,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "0ff7aa0e-0634-49ac-8865-9f8458739c4f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 12,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "86b4e9e3-8edf-4daf-8692-0653cdd68ef6",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 11,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "aadfd161-518d-41e8-9252-b421eaa1d2dc",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 10,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "7b5fc33c-1aae-4198-bca6-21be65b4030c",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 9,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "509bf621-cea7-4085-a9d9-d21241159b40",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 8,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2d497c85-9be9-434a-af32-09e5cd9948a2",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 7,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "dbb2a7fa-2459-4fcf-8063-9f12d809be2f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "08b22865-73c4-4770-8fa4-3bedfa6c5fb7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2019,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "93d4f826-f0ab-43f1-9fea-81d57ed5dab3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d2820a68-e3c0-4506-a731-f952e2058fdd",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 3,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "d4079078-2727-4a71-9278-5e8fae75b2ef",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 2,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "1b17a7fb-b61b-4568-b57c-7c155bfc9e2a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 1,
              "year": 2019,
              "status": "NO_INFO"
            },
            {
              "account_payment_history_id": "7e499a7e-fe95-4474-8713-9fd69eeb6ec4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 12,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "a0c0ebd1-14a0-4ce0-8839-0fa9534423c7",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 11,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "ad4657df-0413-42af-9a71-4177b3c9d308",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 10,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8987320e-e1c4-4d76-8ad0-fe07531da116",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 9,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "407b62af-365b-4cd3-a902-a48eab3cc28f",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 8,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "2e072dd6-bcd3-455f-8123-ef58c9e24960",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 7,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "850e521e-ebf1-4249-9108-1f2d691c6f3e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f0caf55a-824a-4779-9336-aa707df7028e",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "d7e38a52-4bdd-48a3-8d80-72adfd2364b4",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "be30978d-11a2-483b-97d7-27d3d417aeb3",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 3,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "8586a2c4-06cb-437e-9cde-1cb905414d8a",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 2,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "135d7441-cdf7-4147-a1c8-57b35a5462a1",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 1,
              "year": 2020,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b9726058-bdd8-43c0-af7f-a59310cad042",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 6,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "23840fae-6884-4d51-9be9-f48a9ce1e9ee",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 5,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "5e611d3e-993a-4d1f-b809-0c597b49da8d",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 4,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "b2f25de8-92da-4a9d-ad05-73ce1072627b",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 3,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "f21b8280-bb74-4ce9-8149-ef2f614771ec",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 2,
              "year": 2021,
              "status": "CURRENT"
            },
            {
              "account_payment_history_id": "3881e4d1-849b-4bdb-876f-b12d11cd67fe",
              "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
              "account_id": "5638f145-029a-4123-a587-3c77ccf8cd9e",
              "month": 1,
              "year": 2021,
              "status": "CURRENT"
            }
          ]
        }
      ],
      "contact_information": {
        "contact_information_id": "05bfac1f-1b50-4aa2-ad69-ec20e7889521",
        "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
        "first_name": "John",
        "middle_name": "W",
        "last_name": "Smith",
        "full_name": "John W Smith",
        "email": "jsmith@gmail.com",
        "gender": "MALE",
        "marital_status": "MARRIED",
        "annual_household_income_cents": 10000000,
        "is_student": false,
        "is_business_owner": true,
        "primary_address": {
          "address_id": "1f179fac-d587-4f2d-9bf4-6fe78338590e",
          "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
          "number": "123",
          "prefix": null,
          "street": "Main",
          "type": "St",
          "suffix": null,
          "city": "New York",
          "state": "NY",
          "zipcode": "10001",
          "sec_unit_type": null,
          "sec_unit_num": null,
          "full_address": "123 Main Street, New York, NY 10001"
        },
        "addresses": [
          {
            "address_id": "1f179fac-d587-4f2d-9bf4-6fe78338590e",
            "pull_id": "c6f3e62f-ed0c-4266-8014-e7dbd417cbfc",
            "number": "123",
            "prefix": null,
            "street": "Main",
            "type": "St",
            "suffix": null,
            "city": "New York",
            "state": "NY",
            "zipcode": "10001",
            "sec_unit_type": null,
            "sec_unit_num": null,
            "full_address": "123 Main Street, New York, NY 10001"
          }
        ]
      }
    }
  }
}
```

This endpoint retrieves a Pull by Pull ID.

`GET https://api.getcredify.com/v1/pulls/{pullId}`

### Parameters

| Name   | In   | Type         | Required | Description          |
| ------ | ---- | ------------ | -------- | -------------------- |
| pullId | path | string(uuid) | true     | ID of Pull to return |
