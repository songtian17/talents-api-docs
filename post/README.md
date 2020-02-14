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

### Parameters
Body params | Description
--- | ---
imageUri | (required) URI of post image
talentId | (required) ID of talent who post the image

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

## Delete one post
---

`DELETE /post/{id}`

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

`Status 404, "Post not found"`
