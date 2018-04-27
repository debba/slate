# Statistics

The following requests will allow you to show statistics list, count results and export in CSV format.

## Email sent statistics

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/stats/panes/emails?start=:start&end=:end&page=:page&filter=:filter&tz=:tz
`

- `start` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `end` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `page` parameter represents the page number
- `filter` parameter is the status filter, possible values:
    - `*` or not set to get all statuses
    - `NEW`, `DEFER`, `SUCCESS`, `OPEN`, `CLICK`, `REPORT`, `FAIL`, `SYSFAIL`, `UNSUB`, `REPORT`
    - Combination of statuses in array format
- `tz` is the timezone offset (default: `+01:00`)

Some filter combinations:

- Queued emails : `["NEW", "DEFER"]`
- Delivered emails : `["SUCCESS","OPEN","CLICK","UNSUB","REPORT"]`
- Read emails : `["OPEN","CLICK","UNSUB","REPORT"]`
- Bounce emails : `['FAIL', 'SYSFAIL']`

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
        "id":4612864212,
        "subject":"Test for documentation",
        "sender":"christian.serafino@dueclic.com",
        "recipient":"andrea@debbaweb.it",
        "sendTime":"2018-04-24T10:58:06.000Z",
        "status":"SUCCESS",
        "error":null
    },
    {
        "id":4611292665,
        "subject":"Test for documentation #2",
        "sender":"andrea.debernardi@dueclic.com",
        "recipient":"test-dev@dueclic.com",
        "sendTime":"2018-04-23T17:33:02.000Z",
        "status":"OPEN",
        "error":null
    }
]
```

## Count of email sent

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/stats/panes/emails/count?start=:start&end=:end&page=:page&filter=:filter&tz=:tz
`

- `start` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `end` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `page` parameter represents the page number (optional)
- `filter` parameter is the status filter, possible values:
    - `*` or not set to get all statuses
    - `NEW`, `DEFER`, `SUCCESS`, `OPEN`, `CLICK`, `REPORT`, `FAIL`, `SYSFAIL`, `UNSUB`, `REPORT`
    - Combination of statuses in array format
- `tz` is the timezone offset (default: `+01:00`)

Some filter combinations:

- Queued emails : `["NEW", "DEFER"]`
- Delivered emails : `["SUCCESS","OPEN","CLICK","UNSUB","REPORT"]`
- Read emails : `["OPEN","CLICK","UNSUB","REPORT"]`
- Bounce emails : `['FAIL', 'SYSFAIL']`

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
    "count" : 220
}
```

## Export email sent statistics in CSV

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/stats/emails/csv?start_date=:start_date&end_date=:end_date&filter=:filter&tz=:tz
`

- `start_date` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `end_date` parameter is a date formatted as 'YYYY-MM-DD H:i:s'
- `filter` parameter is the status filter, possible values:
    - `*` or not set to get all statuses
    - `NEW`, `DEFER`, `SUCCESS`, `OPEN`, `CLICK`, `REPORT`, `FAIL`, `SYSFAIL`, `UNSUB`, `REPORT`
    - Combination of statuses in array format
- `tz` is the timezone offset (default: `+01:00`)

Some filter combinations:

- Queued emails : `["NEW", "DEFER"]`
- Delivered emails : `["SUCCESS","OPEN","CLICK","UNSUB","REPORT"]`
- Read emails : `["OPEN","CLICK","UNSUB","REPORT"]`
- Bounce emails : `['FAIL', 'SYSFAIL']`