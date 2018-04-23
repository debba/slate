---
title: API Reference

toc_footers:
  - <a href='https://dashboard.serversmtp.com'>Go to turboSMTP dashboard</a>
  
language_tabs:
- json: Request/Response details

includes:
  - errors

search: true
---

# turboSMTP Public API
  
## Version 0.1

This document contains information about turboSMTP's public API. Please report bugs to: <info@turbosmtp.com>

# Getting started
  
## Data interchange format

For the most part (and where not otherwise explicit) turboSMTP’s API uses JSON as the data format of choice when it comes to request and response bodies.

## Authentication (a.k.a. login)

The `auth` value in the response has to be used as a custom cookie for all requests towards turboSMTP's API.

### Request endpoint:

`
GET https://api.turbo-smtp.com/api/authorize/:username/:password
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

