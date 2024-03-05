# User API Spec

## Register User

Endpoint : POST /api/users

Request Body : 

```json
{
  "username" : "fathinmusthafa17",
  "password" : "pasword123",
  "name" : "Fathin Musthafa Habiburrahman"
}
```
Response Body (Success) :

```json
{
  "data" : "OK"
}
```
Response Body (Failed) :

```json
{
  "errors" : "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/auth/login

Request Body :

```json
{
  "username" : "fathinmusthafa17",
  "password" : "pasword123"
}
```
Response Body (Success) :

```json
{
  "data" : {
    "token" : "TOKEN",
    "expiredAt" : 1233554664646 //milisecond
  }
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Username or password wrong ..."
}
```

## Get User

Endpoint : GET /api/users/current

Request Header : 
- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "username" : "fathinmusthafa17",
  "name" : "Fathin Musthafa Habiburrahman"
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Unauthorized..."
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "name" : "Fathin Musthafa Habiburrahman",
  "password" : "newpassword"
}
```

Response Body (Success) :

```json
{
  "username" : "fathinmusthafa17",
  "name" : "Fathin Musthafa Habiburrahman"
}
```
Response Body (Failed, 401) :

```json
{
  "errors" : "Unauthorized..."
}
```

## Logout User

Endpoint : DELETE /api/auth/logout

Request Header :
- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data" : "OK"
}
```