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

# Organizations

## Get Organizations

```shell
curl -w "%{http_code}" "https://hydra-development.herokuapp.com/api/organizations" -H "Authorization:meowmeowmeow"

```

> The above command returns JSON structured like this:

```json
[{"sales_team_id":1,"id":2,"name":"Default Org","description":null,"created_at":"2016-11-15T05:32:39.860Z","updated_at":"2016-11-15T05:32:39.860Z"},{"sales_team_id":1,"id":11,"name":"EMC","description":"Software and hardware company","created_at":"2016-12-24T07:52:25.837Z","updated_at":"2016-12-24T07:54:41.378Z"},{"sales_team_id":1,"id":12,"name":"Google","description":null,"created_at":"2016-12-24T07:55:26.309Z","updated_at":"2016-12-24T07:55:26.309Z"},{"sales_team_id":1,"id":13,"name":"Ebay","description":null,"created_at":"2016-12-24T07:55:38.302Z","updated_at":"2016-12-24T07:55:38.302Z"},{"sales_team_id":1,"id":14,"name":"Apple","description":null,"created_at":"2016-12-24T07:55:55.960Z","updated_at":"2016-12-24T07:55:55.960Z"},{"sales_team_id":1,"id":15,"name":"Oracle","description":null,"created_at":"2016-12-24T07:56:10.606Z","updated_at":"2016-12-24T07:56:10.606Z"}]
```

This endpoint retrieves available phone numbers for the given area code.

### HTTP Request

`GET https://hydra-development.herokuapp.com/api/organizations`

### Query Parameters

Parameter | Description
--------- | -----------
|

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
{
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
}
```

This endpoint retrieves a specific person.


### HTTP Request

`GET https://hydra-development.herokuapp.com/api/people/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the person to retrieve

## Create a Person


```shell
curl "https://hydra-development.herokuapp.com/api/people"
  -H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X POST -d '{ "first_name": "aaa", "last_name": "bbb", "profile_picture": "", "contact_info": [{ "contact_category": "work", "contact_type": "desk phone", "contact_data": "6509898787" }] }'
```

> The above command returns JSON structured like this:

```json
{
  "id": 102,
  "first_name": "aaa",
  "last_name": "bbb",
  "profile_picture": "",
  "organization_id": null,
  "created_at": "2016-11-01T03:24:49.014Z",
  "updated_at": "2016-11-01T03:24:49.014Z",
  "contact_info": [{
    "id": 101,
    "contact_category": "work",
    "contact_type": "desk phone",
    "contact_data": "6509898787",
    "person_id": 102,
    "created_at": "2016-11-01T03:24:49.020Z",
    "updated_at": "2016-11-01T03:24:49.020Z"
  }]
}
```

This endpoint creates a person.


### HTTP Request

`POST https://hydra-development.herokuapp.com/api/people/`

### URL Parameters

Parameter | Description
--------- | -----------


## Update a Specific Person


```shell
curl "https://hydra-development.herokuapp.com/api/people/99" 
-H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X PUT 
-d '{"first_name": "xyz","last_name": "xyz","profile_picture": ""}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 99,
  "first_name": "xyz",
  "last_name": "xyz",
  "profile_picture": "",
  "organization_id": null,
  "created_at": "2016-10-28T18:43:46.473Z",
  "updated_at": "2016-11-01T03:37:40.879Z"
}
```

This endpoint updates a specific person's basic information.


### HTTP Request

`PUT https://hydra-development.herokuapp.com/api/people/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the person to update

## Delete a Specific Person


```shell
curl "https://hydra-development.herokuapp.com/api/people/99" -H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X DELETE
```

> The above command returns an empty respons with OK status


This endpoint deletes a specific person along with associated objects.


### HTTP Request

`DELETE https://hydra-development.herokuapp.com/api/people/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the person to delete

## Get All Contacts for a Specific Person


```shell
curl "https://hydra-development.herokuapp.com/api/people/101/contact_info"
  -H "Authorization:meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[{
  "person_id": 101,
  "id": 100,
  "contact_category": "work",
  "contact_type": "desk phone",
  "contact_data": "6509898787",
  "created_at": "2016-11-01T03:24:18.508Z",
  "updated_at": "2016-11-01T03:24:18.508Z"
}]
```

This endpoint retrieves all contact information objects for a specific person.


### HTTP Request

`GET https://hydra-development.herokuapp.com/api/people/<PERSON_ID>/contact_info`

### URL Parameters

Parameter | Description
--------- | -----------
PERSON_ID | The ID of the person to retrieve

## Get a Specific Contact Info


```shell
curl "https://hydra-development.herokuapp.com/api/people/101/contact_info/100"
  -H "Authorization:meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "person_id": 101,
  "id": 100,
  "contact_category": "work",
  "contact_type": "desk phone",
  "contact_data": "6509898787",
  "created_at": "2016-11-01T03:24:18.508Z",
  "updated_at": "2016-11-01T03:24:18.508Z"
}
```

This endpoint retrieves a specific person.


### HTTP Request

`GET https://hydra-development.herokuapp.com/api/people/<ID>/contact_info/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
PERSON_ID | The ID of the person to retrieve
ID | The ID of the contact info item to retrieve


## Create Contact Info


```shell
curl "https://hydra-development.herokuapp.com/api/people/101/contact_info" -H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X POST -d '{ "contact_category": "work", "contact_type": "internet phone", "contact_data": "6509899999" }'
```

> The above command returns JSON structured like this:

```json
{
  "id": 102,
  "contact_category": "work",
  "contact_type": "internet phone",
  "contact_data": "6509899999",
  "person_id": 101,
  "created_at": "2016-11-01T06:45:45.777Z",
  "updated_at": "2016-11-01T06:45:45.777Z"
}
```

This endpoint created a contact info entry for a specific person.


### HTTP Request

`POST https://hydra-development.herokuapp.com/api/people/<ID>/contact_info`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the person to add contact info entry


## Update a Specific Contact Info


```shell
curl "https://hydra-development.herokuapp.com/api/people/101/contact_info/102" -H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X PUT -d '{ "contact_category": "work", "contact_type": "cell phone", "contact_data": "6509899999" }'
```

> The above command returns JSON structured like this:

```json
{
  "id": 102,
  "contact_category": "work",
  "contact_type": "cell phone",
  "contact_data": "6509899999",
  "person_id": 101,
  "created_at": "2016-11-01T06:45:45.777Z",
  "updated_at": "2016-11-01T06:50:53.895Z"
}
```

This endpoint updates a specific contact info entry.


### HTTP Request

`PUT https://hydra-development.herokuapp.com/api/people/<PERSON_ID>/contact_info/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
PERSON_ID | The ID of the person
ID | The ID of the contact info item to update


## Delete a Specific Contact Info Item


```shell
curl "https://hydra-development.herokuapp.com/api/people/101/contact_info/102" -H "Authorization:meowmeowmeow" -H "Content-Type: application/json" -X DELETE
```

> The above command returns an empty respons with OK status

This endpoint deletes a specific contact info item that belongs to a specific person.


### HTTP Request

`DELETE https://hydra-development.herokuapp.com/api/people/<PERSON_ID>/contact_info/ID`

### URL Parameters

Parameter | Description
--------- | -----------
PERSON_ID | The ID of the person
ID | The ID of the contact info item to update

# Phone Lines

## Get Available Phone Lines

```shell
curl -w '%{http_code}' https://hydra-development.herokuapp.com/api/phone_lines

```

> The above command returns JSON structured like this:

```json
["+16178498655","+16173268684","+16177625529","+16179347767","+16174889425","+16173608701","+16178603060","+16177625190","+16177625245","+16174407211","+16176074487","+16179348254","+16179347230","+16174889421","+16178603646","+16179368793","+16173408773","+16175803369","+16177516484","+16176489887","+16174010476","+16178603263","+16179340031","+16175051855","+16176827547","+16176124257","+16174311276","+16173408474","+16176065854","+16173793689"]
```

This endpoint retrieves available phone numbers for the given area code.

### HTTP Request

`GET https://hydra-development.herokuapp.com/api/phone_lines`

### Query Parameters

Parameter | Description
--------- | -----------
area_code| preferred area code

# Access Tokens

## Retrieve Access Token with Google Token

```shell
curl -w '%{http_code}' "https://hydra-development.herokuapp.com/api/access_tokens" -H "Content-Type: application/json" -X POST -d '{ "g_token":"GOOGLE_ACCESS_TOKEN"}'

```

> The above command returns JSON structured like this:

```json
{"id":10,"auth_token":"yuewejqheu-HlW-HCSUr9qnQw","user_id":3,"created_at":"2016-12-14T03:18:18.081Z","updated_at":"2016-12-14T03:18:18.081Z","device_id":"0"}
```

This endpoint retrieves a Hydra access token.

### HTTP Request

`POST https://hydra-development.herokuapp.com/api/access_tokens`

### Query Parameters

Parameter | Description
--------- | -----------
g_token| Access token issued through Google sign-in