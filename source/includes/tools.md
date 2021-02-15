# Tools

The following requests will allow you to see if turboSMTP tools are enabled / disabled and change.

## Click tracking status

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/tools/clickTracking
`


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

## Open tracking status

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/tools/openingTracking
`


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
  "id": "openingTracking",
  "forced": false,
  "requiredSettings": [],
  "enabled": true,
  "settings": []
}
```

## Enable / disable click tracking

### Request endpoint:

`
PUT https://dashboard.serversmtp.com/api/tools/clickTracking/:action
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

## Enable / disable open tracking

### Request endpoint:

`
PUT https://dashboard.serversmtp.com/api/tools/openingTracking/:action
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
