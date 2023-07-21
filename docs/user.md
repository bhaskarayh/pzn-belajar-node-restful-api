# User API Spec

## Register User API
Endpoint : POST /api/users

Request Body:

```json
{
    "username": "pzn",
    "password": "rahasia",
    "name": "Programmer Zaman Now"
}
```
Response Body Success:

```json
{
    "data":{
        "username": "pzn",
        "name": "Programmer Zaman Now"
    }
}
```
Response Body Error:

```json
{
    "error": "Username already registered"
}
```


## Login User API
Endpoint : POST /api/users/login

Request Body:

```json
{
    "username": "pzn",
    "password": "rahasia",
}
```
Response Body Success:

```json
{
    "data":{
        "token": "unique-token"
    }
}
```
Response Body Error:

```json
{
    "error": "Username or password wrong"
}
```

## Update User API
Endpoint : PATCH /api/users/current

Headers:
- Authorization : token

Request Body:

```json
{
    "name": "Programmer Zaman Now lagi", // optional
    "password": "new password", // optional
}
```
Response Body Success:

```json
{
    "data":{
        "username": "pzn",
        "name": "Programmer Zaman Now lagi",
    }
}
```
Response Body Error:

```json
{
    "error": "Name length max 100"
}
```

## Get User API
Endpoint : GET /api/users/current

Headers:
- Authorization : token

Response Body Success:

```json
{
    "data":{
        "username": "pzn",
        "name": "Programmer Zaman Now lagi",
    }
}
```
Response Body Error:

```json
{
    "error": "Unauthorized"
}

## Logout User API
Endpoint : DELETE /api/users/logout

Headers:
- Authorization : token

Response Body Success:

```json
{
    "data": "OK"
}
```
Response Body Error:

```json
{
    "error": "Unauthorized"
}