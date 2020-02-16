# Comment

## Get comments
---
Get list of comments by post id

`GET /comment/{id}`

### Parameters
URL params | Description
--- | ---
id | (required) ID of post

### Example
`GET /comment/4`

### Response
```
200

[
    {
        "id": 4,
        "content": "Good pic!!!!!!!",
        "authorId": 1,
        "postId": 3,
        "createdAt": "2020-02-13T03:56:04.482Z",
        "author": {
            "id": 1,
            "name": "Davy Jones ASD",
            "username": "dj_dj",
            "profileImageUri": "https://cscassignment.s3.amazonaws.com/2ad5e165-ba64-4290-b752-65714d9693c4-bustle_102416_306.jpg",
            "bio": "Welcome to Davy Jones' locker!\nNICE GUYasda",
            "createdAt": "2020-02-12T11:01:37.216Z",
            "updatedAt": "2020-02-13T05:37:19.490Z"
        }
    }
    ...
]
```

## Create comment
---
Create new comment

`POST /comment/{id}`

### Request headers
Headers | Description
--- | ---
Authorization: Bearer `token` | `token`: Session token returned by auth service

### Parameters
URL params | Description
--- | ---
id | (required) ID of post

Body params | Description
--- | ---
content | (required) Content of the comment
authorId | (required) ID of talent who make the comment

### Example
```
POST /comment/4
{
    "content": "Beautiful scenery!",
    "authorId": 2
}
```

### Response
> Success

`Status 201, "Comment created"`

> Failure

`Status 403`