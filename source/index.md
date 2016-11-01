---
title: Hydra API Reference

language_tabs:
  - curl


includes:
  - errors

search: true
---

# Introduction

Welcome to the Hydra API. You can use our API to access the object model and perform CRUD operations.

You can view code examples in the dark area to the right. The api endpoint in the examples is for our development environment.


# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://hydra-development.herokuapp.com/api" -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with the user's authorization token.

Hydra uses authorization tokens to allow access to the API.

The API expects for the authorization token to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace `meowmeowmeow` with the user's authorization token.
</aside>

# People

## Get All People


```shell
curl "https://hydra-development.herokuapp.com/api/people"
  -H "Authorization:meowmeowmeow" 
```

> The above command returns JSON structured like this:

```json
[{
  "id": 98,
  "first_name": "Selina",
  "last_name": "Reinger",
  "profile_picture": null,
  "organization_id": null,
  "created_at": "2016-10-28T18:43:46.463Z",
  "updated_at": "2016-10-28T18:43:46.463Z",
  "contact_info": [{
    "person_id": 98,
    "id": 98,
    "contact_category": "desk phone",
    "contact_type": "home",
    "contact_data": "(259) 975-7892",
    "created_at": "2016-10-28T18:43:46.468Z",
    "updated_at": "2016-10-28T18:43:46.468Z"
  }]
}, {
  "id": 99,
  "first_name": "Kay",
  "last_name": "Lang",
  "profile_picture": null,
  "organization_id": null,
  "created_at": "2016-10-28T18:43:46.473Z",
  "updated_at": "2016-10-28T18:43:46.473Z",
  "contact_info": [{
    "person_id": 99,
    "id": 99,
    "contact_category": "fax",
    "contact_type": "home",
    "contact_data": "(289) 853-6383",
    "created_at": "2016-10-28T18:43:46.478Z",
    "updated_at": "2016-10-28T18:43:46.478Z"
  }]
}]
```

This endpoint retrieves all people records owned by the user. The results include the contact info objects associated with each person.

### HTTP Request

`GET https://hydra-development.herokuapp.com/api/people`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------



## Get a Specific Person


```shell
curl "https://hydra-development.herokuapp.com/api/people/99"
  -H "Authorization:meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{"id":99,"first_name":"Kay","last_name":"Lang","profile_picture":null,"organization_id":null,"created_at":"2016-10-28T18:43:46.473Z","updated_at":"2016-10-28T18:43:46.473Z","contact_info":[{"person_id":99,"id":99,"contact_category":"fax","contact_type":"home","contact_data":"(289) 853-6383","created_at":"2016-10-28T18:43:46.478Z","updated_at":"2016-10-28T18:43:46.478Z"}]}
```

This endpoint retrieves a specific person.


### HTTP Request

`GET https://hydra-development.herokuapp.com/api/people/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the person to retrieve

