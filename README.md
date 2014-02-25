Celsius wiki
============
------------

### Base URL 
    https://<host_url>/


------------

## Auth

### Account

#### Create new account
    /auth/account

##### Method `POST`
##### Content-Type `application/json`

##### Request JSON object
```
{
    "email": "STRING",
    "password": "STRING"
}
```

##### Response JSON object
  -if OK `{apikey: STRING}`
  
  -if error `500`

  -----
#### Reset password
    /auth/account
##### Method `PATCH`
##### Content-Type `application/json`

##### Request JSON object
```
{"email": STRING}
```
##### Response JSON object
  -if OK `200`
  
  -if error `500`


#### Change password
    /auth/account
##### Method `PUT`
##### Content-Type `application/json`

##### Request JSON object
```
{
    "email": STRING,
    "password": STRING
}
```
##### Response JSON object
  -if OK `200`
  
  -if error `500`

  -----
### Login
    /auth/login

##### Method `POST`
##### Content-Type `application/json`
  
##### Request JSON object
```
{
    "email": "STRING",
    "password": "STRING"
}
```
##### Response JSON object
  -if OK `{apikey: STRING}`
  
  -if error `401`

-----------

## REST API
#### Version `1`
#### Base URL 
    https://<host_url>/api/v1

#### Permission
All requests requires apikey authentication
`?apikey=9656439238839`

## Resources

### Contact
Permission: apikey

##### Create a list of contacts
    /contact
    
##### Method `POST`
##### Content-Type `application/json`

##### Request JSON object
```
{ "data": [
            {
                "first": STRING,
                "last": STRING,
                "phone": {
                  "mobile": STRING,
                  "iphone": STRING,
                  "work": STRING,
                  "home": STRING
                },
                "email":  STRING
            },
            ...
        ]
}
```
##### Response JSON object
  -if OK `200`
  
  -if error: `JSON STRING with the error message`


#### Get a list of contacts
    /contact
    
#### Method `GET`
  
##### Response JSON object
```
[   
    {
        "first": STRING,
        "last": STRING,
        "phone": {
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
  -if error: `JSON STRING with the error message`
  
------------

### Photo [not finished]


------------
## References:
- [Internet Media Type](http://en.wikipedia.org/wiki/Internet_media_type)
- [HTTP](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) 








