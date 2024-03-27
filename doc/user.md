# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "hary",
  "password": "secret",
  "name": "Hary Arrahman"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "hary",
    "name": "Hary Arrahman"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username already registered"
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "hary",
  "password": "secret"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "hary",
    "name": "Hary Arrahman",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Username or password is wrong"
}
```

## Get User

Endpoint : GET /api/users/current

Headers :

- Authorization: token

Response Body (Success) :

```json
{
  "data": {
    "username": "hary",
    "name": "Hary Arrahman"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint : PATCH /api/users/current

Headers :

- Authorization: token

Request Body :

```json
{
  "password": "secret", // optional, if want to change password
  "name": "Hary Arrahman" // optional, if want to change name
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "hary",
    "name": "Hary Arrahman"
  }
}
```

## Logout User

Endpoint : DELETE /api/users/current

Headers :

- Authorization: token

Response Body (Success) :

```json
{
  "data": true
}
```
