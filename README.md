# Celsius app - server


### Base URL `?`


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


### Get auth token
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
}
```

> status `500` || `401` body `{message: <error>}`

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
            "main": STRING,
            "mobile": STRING,
            "iphone": STRING,
            "work": STRING,
            "home": STRING
        },
        "email":  STRING
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
          "main": STRING,
          "mobile": STRING,
          "iphone": STRING,
          "work": STRING,
          "home": STRING
        },
        "email":  STRING,
    },
    ...
]
```
> status `500` body `{message: <error>}`
