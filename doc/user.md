# User API Spec

## Register User

endpoint : POST/api/users

Request Body :

```json
{
  "username": "Rendi",
  "password": "rahasia",
  "name": "Rendi Sutendi"
}
```

Response Body (Succes):

```json
{
  "data": {
    "username": "rendi",
    "name": "Rendi Sutendi"
  }
}
```

Response Body (Failed):

```json
{
  "errors": {
    "username": "Username Already Registered !"
  }
}
```

## Login User

endpoint : POST/api/users/login

Request Body :

```json
{
  "username": "Rendi",
  "password": "rahasia"
}
```

Response Body (Succes):

```json
{
  "data": {
    "username": "rendi",
    "name": "Rendi Sutendi",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed):

```json
{
  "errors": {
    "username": "Username Or Password Is Wrong !"
  }
}
```

## Get User

endpoint : Get/api/users/current

Headers :

- Authorization : token

Response Body (Succes):

```json
{
  "data": {
    "username": "rendi",
    "name": "Rendi Sutendi"
  }
}
```

Response Body (Failed):

```json
{
  "errors": {
    "username": "Unauthorization"
  }
}
```

## Update User

endpoint : PATCH/api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "password": "rahasia", //Optional , if want to change password
  "name": "Rendi Sutendi" //optional, if want ti change name
}
```

Response Body (Succes):

```json
{
  "data": {
    "username": "rendi",
    "name": "Rendi Sutendi"
  }
}
```

## Logout User

Endpoint : DELETE/api/users/current

Headers :

- Authorization : tokern

Responser Body (Succes) :

```json
{
  "data": true
}
```
