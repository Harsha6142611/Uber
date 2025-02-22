# Uber
# User Registration Endpoint

## Endpoint: `/users/register`


## Endpoint: `/users/login`

**Method:** `POST`

**Description:** This endpoint logs in an existing user.

**Request Body:**
```json
{
    "email": "john.doe@example.com",
    "password": "password123"
}
```

**Response Body:**
```json
{
    "token": "jwt_token_here",
    "user": {
        "_id": "user_id_here",
        "fullname": {
            "firstname": "John",
            "lastname": "Doe"
        },
        "email": "john.doe@example.com",
        "password": "hashed_password_here",
        "socketId": null
    }
}
```

**Error Response Body:**
```json
{
    "errors": [
        {
            "msg": "Invalid Email or Password",
            "param": "email",
            "location": "body"
        }
    ],
    "message": "Authentication failed"
}
```

**Description:** This endpoint registers a new user.

**Request Body:**
```json
{
  "fullname": {
    "firstname": "John",
    "lastname": "Doe"
  },
  "email": "john.doe@example.com",
  "password": "password123"
}
```

**Response Body:**
```json
{
  "token": "jwt_token_here",
  "user": {
    "_id": "user_id_here",
    "fullname": {
      "firstname": "John",
      "lastname": "Doe"
    },
    "email": "john.doe@example.com",
    "password": "hashed_password_here",
    "socketId": null
  }
}
```

**Error Response Body:**
```json
{
  "errors": [
    {
      "msg": "Invalid Email",
      "param": "email",
      "location": "body"
    },
    {
      "msg": "First name must be at least 3 characters long",
      "param": "fullname.firstname",
      "location": "body"
    },
    {
      "msg": "Password must be at least 6 characters long",
      "param": "password",
      "location": "body"
    }
  ],
  "message": "User already exist"
}
```