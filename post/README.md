# Post

## Get posts
---
Get list of posts

`GET /post?user={user}&limit={limit}&page={page}`

### Parameters
Query params | Description
--- | ---
user | (optional) ID of talent
limit | (optional) Number of posts to return. Default: 25
page | (optional) Page number. Default: 1

### Example
`GET /post?user=1&limit=3&page=2`

### Response

> Success

```
Status 200

[
    {
        "id": 2,
        "imageUri": "https://via.placeholder.com/600/92c952",
        "talentId": 1,
        "createdAt": "2020-02-12T07:09:28.917Z",
        "comments": [...],
        "talent": {...}
    },
    ...
]
```

## Get one post
---
Get one post by id

`GET /post/{id}`

### Parameters
URL params | Description
--- | ---
id | (optional) ID of post

### Example
`GET /post/4`

### Response
> Success

```
Status 200

{
    "id": 4,
    "imageUri": "https://via.placeholder.com/600/92c952",
    "talentId": 1,
    "createdAt": "2020-02-12T07:09:28.917Z",
    "comments": [...],
    "talent": {...}
},
```

> Failure

`Status 404, "Post not found"`

## Create one post
---
Create one post

`POST /post`

### Request headers
Headers | Description
--- | ---
Authorization: Bearer `token` | `token`: Session token returned by auth service

### Parameters

Body params | Description
--- | ---
imageUri | (required) URI of post image
talentId | (required) ID of talent who post the image
visibility | (optional) Visibility of post. 'public' or 'private'. Default: 'public'

### Example
```
POST /post

{
	"imageUri": "https://via.placeholder.com/600/92c952",
	"talentId": 1
}
```

### Response
> Success

`Status 201, "Post created"`

> Failure

`Status 403`

## Update one post
---

`PUT /post/{id}`

### Request Headers
Headers | Description
--- | ---
Authorization: Bearer `token` | `token`: Session token returned by auth service

### Parameters
URL params | Description
--- | ---
id | (required) ID of post

Body params | Description
--- | ---
visibility | (optional) Visibility of post. 'private' or 'public'

### Example
```
PUT /post/4

{
    "visibility": "private"
}
```

### Response
> Success

`Status 200, "Post updated"`

> Failure

`Status 403`

`Status 404, "Post not found"`

## Delete one post
---

`DELETE /post/{id}`

### Request headers
Headers | Description
--- | ---
Authorization: Bearer `token` | `token`: Session token returned by auth service

### Parameters
URL params | Description
--- | ---
id | (required) ID of post

### Example
`DELETE /post/4`

### Response
> Success

`Status 200, "Post deleted"`

> Failure

`Status 403`

`Status 404, "Post not found"`
