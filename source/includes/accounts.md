# Accounts

The following requests will allow you to show accounts info.

## Account info

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/user/info
`

No params needed.

<aside class="notice">
<strong>NOTE:</strong> <em>The response body shown here aside is just a convenient subset of the real whole response.</em>
</aside> 

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
  "passwd":"",
  "active":true,
  "email":"andrea@emailchef.com",
  "gateway":"q1",
  "ip":3350965831,
  "accountid":18897904
  ...
}
```

## Active plans

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/plans
`

No params needed.

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
[{
    "id": 1,
    "accountID": 584,
    "smtp_limit": 200,
    "smtp_limit_interval": "Daily",
    "plan_expiration": "2019-01-04T00:00:00.000Z",
    "smtp_count": 1,
    "last_used": "2018-04-24T08:58:06.000Z",
    "parentid": null,
    "expired": 0,
    "active": true
}, {
    "id": 2,
    "accountID": 584,
    "smtp_limit": 100000,
    "smtp_limit_interval": "Monthly",
    "plan_expiration": "2018-05-03T00:00:00.000Z",
    "smtp_count": 0,
    "last_used": "2018-04-04T08:47:16.000Z",
    "parentid": null,
    "expired": 0,
    "active": true
}]

```

## Subaccounts list

### Request endpoint:

`
GET https://dashboard.serversmtp.com/api/useraccounts/summary
`

No params needed.

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
[{
     "id": 584,
     "email": "subaccount@dueclic.com",
     "active": true,
     "ip": "199.244.75.99",
     "sent": 3,
     "limit": -1,
     "reputation": 5
 }]

```