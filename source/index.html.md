---
title: API Reference

toc_footers:
  - <a href='https://dashboard.serversmtp.com'>Go to turboSMTP dashboard</a>
  
language_tabs:
- json: Request/Response details

includes:
  - reports
  - statistics
  - errors

search: true
---

# turboSMTP Public API
  
## Version 0.1

This document contains information about turboSMTP's public API. Please report bugs to: <info@turbosmtp.com>

# Getting started
  
## Data interchange format

For the most part (and where not otherwise explicit) turboSMTP’s API uses JSON as the data format of choice when it comes to request and response bodies.

## Accessing resources

Authorization to access a user’s resource is granted to clients provided they set a authentication cookie into their request, valued with the proper authentication key issued by turboSMTP servers. The authentication key is user-based and it is issued by turboSMTP servers upon successful user’s email address + password challenge, performed by means of appropriate request.

As an example, such cookie should look like what follows:

`authorizationKey: 44cf4c36d0e9cbe32f6fd83ff69a9df3b6212828c`

## Authentication (a.k.a. login)

The `auth` value in the response has to be used as a custom cookie for all requests towards turboSMTP's API.

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/authorize/:username/:password
`

- `username` is the email of turboSMTP account
- `password` is the password of turboSMTP account

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body (successful authentication):

```json
{
    "auth" : "44cf4c36d0e9cbe32f6fd83ff69a9df3b6212828c"
}
```

> Response body (unsuccessful authentication):

```json
{
    "errorCode" : 1,
    "message": "Wrong credentials specified"
}
```