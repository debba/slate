# Reports

The following requests will allow you to show a reports list, count results, delete a single instance and export in CSV format.

## Reports by type in time range

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type?start=:start&end=:end&page=:page&filter=:filter&tz=:tz
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `start` parameter is a date formatted as 'YYYY-MM-DD'
- `end` parameter is a date formatted as 'YYYY-MM-DD'
- `page` parameter represents the page number
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
[
    {
        "cid": 323223135,
        "email": "andrea.colombini@dueclic.com",
        "ts": "2018-03-27T06:31:42.000Z",
        "response": "62.149.128.154 does not like recipient. Remote host said: 550 5.1.1 <andrea.colombini@dueclic.com> : sorry, no mailbox here by that name (#5.1.1 - chkuser) {1.2.3.4} Giving up on 1.2.3.4. "
    }
]
```

## Count reports by type in time range

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type/count?start=:start&end=:end&page=:page&filter=:filter&tz=:tz
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `start` parameter is a date formatted as 'YYYY-MM-DD'
- `end` parameter is a date formatted as 'YYYY-MM-DD'
- `page` parameter represents the page number
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
{
    "count" : 1
}
```

## Export reports in CSV by type in time range

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type/csv?start=:start&end=:end&page=:page&filter=:filter&tz=:tz
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `start` parameter is a date formatted as 'YYYY-MM-DD'
- `end` parameter is a date formatted as 'YYYY-MM-DD'
- `page` parameter represents the page number
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)

## All reports by type

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type/all?page=:page&filter=:filter&tz=:tz
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `page` parameter represents the page number
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
[
    {
        "cid": 323223135,
        "email": "andrea.debernardi@dueclic.com",
        "ts": "2018-03-27T06:31:42.000Z",
        "response": "62.149.128.154 does not like recipient. Remote host said: 550 5.1.1 <andrea.debernardi@dueclic.com> : sorry, no mailbox here by that name (#5.1.1 - chkuser) {1.2.3.4} Giving up on 1.2.3.4. "
    }
]
```

## Count all reports by type

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type/all/count?filter=:filter&tz=:tz&page=:page
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)
- `page` parameter represents the page number (optional)

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
{
    "count" : 520
}
```

## Export all reports in CSV by type

### Request endpoint:

`
GET https://dashboard.serversmtp.com/web/api/reports/:type/all/csv?filter=:filter&tz=:tz&page=:page
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `start` parameter is a date formatted as 'YYYY-MM-DD'
- `end` parameter is a date formatted as 'YYYY-MM-DD'
- `page` parameter represents the page number
- `filter` parameter is the search filter
- `tz` is the timezone offset (default: `+01:00`)
- `page` parameter represents the page number (optional)

## Delete report by type

### Request endpoint:

`
DELETE https://dashboard.serversmtp.com/web/api/reports/:type?ids=:ids
`

- `type` parameter represents the type of report, possible values are:
    - `bounce` for bounces
    - `spam` for spam
    - `unsub` for unsubscriptions
- `ids` comma separated reports id to delete

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
{
    "success" : true
}
```

## Delete all spam reports

### Request endpoint:

`
DELETE https://dashboard.serversmtp.com/web/api/reports/spam/all
`

No params needed

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body:

```json
{
    "success" : true
}
```