# Talent

## Get all talents
---
Get list of all talents

`
GET /talent
`

### Response
```
[
    {
        "id": 1,
        "name": "Louie Leach",
        "username": "louiel",
        "profileImageUri": "https://via.placeholder.com/600/92c952",
        "bio": "Welcome to my page!",
        "createdAt": "2020-02-12T11:01:37.216Z",
        "updatedAt": "2020-02-12T11:01:37.216Z"
    },
    {
        "id": 2,
        "name": "John Paul Jones",
        "username": "jpj",
        "profileImageUri": "https://via.placeholder.com/600/92c952",
        "bio": "Hi I'm John Paul Jones",
        "createdAt": "2020-02-12T11:03:01.100Z",
        "updatedAt": "2020-02-12T11:03:01.100Z"
    }
]
```

## Get talent by username
---
Get one talent by username

`GET /talent/username/{username}`

### Parameters
URL params | Description
--- | ---
username | (required) Username of talent

### Example
```
GET /talent/username/jpj
```

### Response
> Success

`Status 200`
```
{
    "id": 2,
    "name": "John Paul Jones",
    "username": "jpj",
    "profileImageUri": "https://via.placeholder.com/600/92c952",
    "bio": "Hi I'm John Paul Jones",
    "createdAt": "2020-02-12T11:03:01.100Z",
    "updatedAt": "2020-02-12T11:03:01.100Z"
}
```

> Failure

`Status 404, "Talent not found"`

## Get talent by ID
---
Get one talent by id

`
GET /talent/{id}
`

### Parameters
URL params | Description
--- | ---
id | (required) ID of talent

### Example
```
GET /talent/1
```

### Response
> Success

`Status 200`
```
{
    "id": 1,
    "name": "Louie Leach",
    "username": "louiel",
    "profileImageUri": "https://via.placeholder.com/600/92c952",
    "bio": "Welcome to my page!",
    "createdAt": "2020-02-12T11:01:37.216Z",
    "updatedAt": "2020-02-12T11:01:37.216Z"
}
```
> Failure

`Status 404, "Talent not found"`

## Create talent
---
Create new talent

`
POST /talent
`

### Parameters
Body params | Description
---|---
accountId | (required) ID of account linked to talent
name | (required) Name of talent
username | (required) Username of talent
profileImageUri | (optional) URI of profile picture
bio | (optional) Bio of talent


### Example
```
POST /talent

{
    "accountId": "1",
    "name": "Mason Dale",
    "username": "MasonD",
    "profileImageUri": "https://via.placeholder.com/600/92c952",
    "bio": "Industrial production manager @ Road Runner Lawn Services"
}
```

### Response
> Success

`Status 201, "Talent created"`

## Update talent
---
Update one existing talent

`PUT /talent/{id}`

### Request headers
Headers | Description
--- | ---
Authorization: Bearer `token` | `token`: Session token returned by auth service

### Parameters
URL params | Description
--- | ---
id | (required) ID of talent

Body params | Description
--- | ---
name | (optional) Name of talent
username | (optional) Username of talent
profileImageUri | (optional) URI of profile picture
bio | (optional) Bio of talent
isSubscribed | (options) If talent is allowed to search. true or false

### Example
```
POST /talent/1

{
    "name": "Mason Dale",
    "username": "MasonD",
    "profileImageUri": "https://via.placeholder.com/600/92c952",
    "bio": "New bio!"
}
```

### Response
> Success

`Status 200, "Talent updated"`

> Failure

`Status 403`

`Status 404, "Talent not found"`

## Delete talent
---
Delete one talent by id

`DELETE /talent/{id}`

### Parameters
URL params | Description
--- | ---
id | (required) ID of talent

### Example
`DELETE /talent/1`

### Response

> Success

`Status 200, "Talent deleted"`

> Failure

`Status 404, "Talent not found"`