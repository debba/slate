# Tools

The following requests will allow you to enable / disable some turboSMTP tools.

## Click tracking - enable / disable

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/tools/clickTracking/:action
`

- `action` param, possible values are: `enable` or `disable`

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body (in case of enabling):

```json
{
    "id": "clickTracking",
    "forced": false,
    "requiredSettings": [],
    "enabled": true,
    "settings": [
        {
            "key": "clicktracking",
            "value": true
        },
        {
            "key": "clicktracking_plaintext",
            "value": false
        }
    ]
}
```

## Open tracking - enable / disable

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/tools/openingTracking/:action
`

- `action` param, possible values are: `enable` or `disable`

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body (in case of disabling):

```json
{
    "id": "openingTracking",
    "forced": false,
    "requiredSettings": [],
    "enabled": false,
    "settings": []
}
```