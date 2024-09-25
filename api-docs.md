# API Documentation

This document provides details about the available API endpoints for the VidTube project.

## Authentication

### `POST /tokens`
Generates a new authentication token.

**Request**:
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response**:
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsIn..."
}
```

---

## User Management

### `GET /users`
Retrieves a list of users. (Requires authentication)

**Response**:
```json
[
  {
    "id": "user1",
    "email": "user1@example.com",
    "name": "John Doe"
  },
  {
    "id": "user2",
    "email": "user2@example.com",
    "name": "Jane Doe"
  }
]
```

### `POST /users`
Creates a new user.

**Request**:
```json
{
  "email": "newuser@example.com",
  "password": "password123",
  "name": "New User"
}
```

**Response**:
```json
{
  "id": "new_user_id",
  "message": "User created successfully"
}
```

### `POST /users/signin`
Logs in a user and returns an authentication token.

**Request**:
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response**:
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsIn..."
}
```

### `GET /users/:id`
Fetches a single user by ID. (Requires authentication)

**Response**:
```json
{
  "id": "user_id",
  "email": "user@example.com",
  "name": "User Name"
}
```

### `PATCH /users/:id`
Updates a user's information. (Requires authentication)

**Request**:
```json
{
  "name": "Updated User"
}
```

**Response**:
```json
{
  "message": "User updated successfully"
}
```

### `DELETE /users/:id`
Deletes a user by ID. (Requires authentication)

**Response**:
```json
{
  "message": "User deleted successfully"
}
```

---

## Video Management

### `GET /videos`
Retrieves a list of public videos.

**Response**:
```json
[
  {
    "id": "video1",
    "title": "First Video",
    "author": "Author Name",
    "views": 1234,
    "likes": 100,
    "dislikes": 5
  }
]
```

### `GET /videos/:id`
Retrieves the details of a specific video.

**Response**:
```json
{
  "id": "video1",
  "title": "First Video",
  "description": "This is the first video.",
  "author": "Author Name",
  "views": 1234
}
```

### `POST /videos/:id`
Fetches video recommendations based on the video ID.

**Response**:
```json
[
  {
    "id": "recommended_video_1",
    "title": "Recommended Video 1",
    "views": 5432
  }
]
```

### `POST /users/:id/videos`
Uploads a new video for the specified user. (Requires authentication)

**Request**:
- Multipart form data including fields for `img` and `video` files.

**Response**:
```json
{
  "message": "Video uploaded successfully"
}
```

### `PATCH /users/:id/videos/:pid`
Updates an existing video. (Requires authentication)

**Request**:
- Multipart form data including updated `img` or `video` files.

**Response**:
```json
{
  "message": "Video updated successfully"
}
```

### `DELETE /users/:id/videos/:pid`
Deletes a specific video. (Requires authentication)

**Response**:
```json
{
  "message": "Video deleted successfully"
}
```

### `PATCH /videos/:id/like`
Likes a specific video. (Requires authentication)

**Response**:
```json
{
  "message": "Video liked"
}
```

### `PATCH /videos/:id/dislike`
Dislikes a specific video. (Requires authentication)

**Response**:
```json
{
  "message": "Video disliked"
}
```

---

## Comment Management

### `GET /comments`
Fetches a list of comments for a video.

**Response**:
```json
[
  {
    "id": "comment1",
    "author": "User1",
    "text": "Great video!"
  }
]
```

### `POST /comments`
Creates a new comment. (Requires authentication)

**Request**:
```json
{
  "text": "This is a comment."
}
```

**Response**:
```json
{
  "message": "Comment created successfully"
}
```

### `GET /comments/:id`
Fetches a specific comment by its ID.

**Response**:
```json
{
  "id": "comment1",
  "author": "User1",
  "text": "Great video!"
}
```

### `PATCH /users/:id/comments`
Updates a specific comment. (Requires authentication)

**Request**:
```json
{
  "text": "Updated comment text"
}
```

**Response**:
```json
{
  "message": "Comment updated successfully"
}
```

### `DELETE /users/:id/comments`
Deletes a specific comment. (Requires authentication)

**Response**:
```json
{
  "message": "Comment deleted successfully"
}
```

### `PATCH /:id/like`
Likes a specific comment. (Requires authentication)

**Response**:
```json
{
  "message": "Comment liked"
}
```

### `PATCH /:id/dislike`
Dislikes a specific comment. (Requires authentication)

**Response**:
```json
{
  "message": "Comment disliked"
}
```

---

## Error Handling

All endpoints can return the following error codes:

- **400 Bad Request**: Invalid input data.
- **401 Unauthorized**: Authentication required or failed.
- **404 Not Found**: Resource not found.
- **500 Internal Server Error**: Server encountered an error.

---

## Conclusion

This API allows users to manage videos, comments, and users, as well as authenticate and interact with video content through likes, dislikes, and recommendations. Authentication is required for certain actions, such as creating, updating, or deleting content.
