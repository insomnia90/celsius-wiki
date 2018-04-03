# Celsius app - server


### Base URL `<base_url>`


### Create new user
##### URL: `/users`
##### Method `POST`
##### Content-Type `application/json`
##### Request body
```
{
    "email": "STRING",
    "password": "STRING"
}
```
##### Response body
> status `200`

> status `500` body `{message: <error>}`


### Get auth token (Login)
##### URL: `/auth/token`
##### Method `POST`
##### Content-Type `application/json`
##### Request body
```
{
    "email": "STRING",
    "password": "STRING"
}
```
##### Response body
> status `200` body
```
{
    success: true,
    exp: '72h', // expiration date
    token: token,
    len: <contacts count>
}
```

> status `500` || `401` body `{message: <error>}`

### Reset password
##### URL: `/auth/account`
##### Method `PATCH`
##### Content-Type `application/json`
##### ! No Access-Token required
##### Request body
```
{
    "email": <email>
}
```
##### Response body
> status `200`

> status `500` body `{message: <error>}`

### Update password
##### URL: `/auth/account`
##### Method `PUT`
##### Content-Type `application/json`
Add in the HTTP Header
##### X-Access-Token `<token>`
##### Request body
```
{
    "password": <new_password>
}
```
##### Response body
> status `200`

> status `500` body `{message: <error>}`


-----------

## REST API

#### Permission
Add in the HTTP Header
##### X-Access-Token `<token>`

-----------

### Contact

#### Create a list of contacts
##### URL: `/contacts`
##### Method `POST`
##### Content-Type `application/json`

##### Request body: array
```
[
    {
        "first": STRING,
        "last": STRING,
        "phone": {
            "main": [STRING] : array of strings,
            "mobile": [STRING],
            "iphone": [STRING],
            "work": [STRING],
            "home": [STRING],
            "other": [STRING]
        },
        "email": STRING(valid email format)
    },
    ...
]
```
##### Response body
> status `200`

> status `500` body `{message: <error>}`


#### Get a list of contacts
##### URL: `/contacts`
##### Method `GET`
##### Content-Type `application/json`
##### Response body
> status `200`
```
[   
    {
        "first": STRING,
        "last": STRING,
        "phone": {
            "main": [STRING] : array of strings,
            "mobile": [STRING],
            "iphone": [STRING],
            "work": [STRING],
            "home": [STRING],
            "other": [STRING]
        },
        "email": STRING(valid email format)
    },
    ...
]
```
> status `500` body `{message: <error>}`
