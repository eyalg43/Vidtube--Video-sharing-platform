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

Response:
{
  "token": "eyJhbGciOiJIUzI1NiIsIn..."
}

## User Management

### GET /users
Retrieves a list of users. (Requires authentication)

response:
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

### POST /users
Creates a new user.

Request:
{
  "email": "newuser@example.com",
  "password": "password123",
  "name": "New User"
}

Response:
{
  "id": "new_user_id",
  "message": "User created successfully"
}

### POST /users/signin
Logs in a user and returns an authentication token.

Request:
{
  "email": "user@example.com",
  "password": "password123"
}

Response:
{
  "token": "eyJhbGciOiJIUzI1NiIsIn..."
}

### GET /users/:id
Fetches a single user by ID. (Requires authentication)

Response:
{
  "id": "user_id",
  "email": "user@example.com",
  "name": "User Name"
}

### PATCH /users/:id
Updates a user's information. (Requires authentication)

Request:
{
  "name": "Updated User"
}

Response:
{
  "message": "User updated successfully"
}

### DELETE /users/:id
Deletes a user by ID. (Requires authentication)

Response:
{
  "message": "User deleted successfully"
}

##
