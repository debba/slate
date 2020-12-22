# Errors

## General errors
The turboSMTP API uses the following error codes:

Error Type | Meaning
---------- | -------
1 | Invalid authorization credentials
2 | Provided account is inactive. Maybe you are banned.
3 | Invalid authorization token
4 | Resource not found
5 | Server system error
6 | Concurrent modification exception
7 | Access to requested resources is denied

## Send Api errors




- Missing username/password

<pre class="mid-pre">{
    "errorCode": 3,
    "message": "Invalid authorization token",
    "details": "No authorization key was specified for request: POST /api/mail/send"
}
</pre>

- Invalid username/password

<pre class="mid-pre">{
    "error": 3,
    "message": "Wrong credentials specified"
}
</pre>

- Missing sender

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        "missing or not valid sender email (from)"
    ]
}
</pre>

- Missing recipients

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        "missing recipients (to)"
    ]
}
</pre>

- Invalid recipients (to-cc-bcc)

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        [
            "'INVALID_EMAIL' 'to' email not valid"
        ]
    ]
}
</pre>


- Invalid Mime

<pre class="mid-pre">{
    "message": "error",
    "errors": {
        "message": "error",
        "errors": "Invalid Mime"
    }
}
</pre>

- No enough credit in account subscription

<pre class="mid-pre">{
    "message": "error",
    "errors": {
        "message": "error",
        "errors": "nocredit"
    }
}
</pre>

- deactivated account

<pre class="mid-pre">{
    "error": 3,
    "message": "Account for  test@domain.com  is inactive"
}
</pre>