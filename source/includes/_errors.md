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




<h3>Missing username/password</h3>

<pre class="mid-pre">{
    "errorCode": 3,
    "message": "Invalid authorization token",
    "details": "No authorization key was specified for request: POST /api/mail/send"
}
</pre>

<h3>Invalid username/password</h3>

<pre class="mid-pre">{
    "error": 3,
    "message": "Wrong credentials specified"
}
</pre>

<h3>Missing sender</h3>

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        "missing or not valid sender email (from)"
    ]
}
</pre>

<h3>Missing recipients</h3>

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        "missing recipients (to)"
    ]
}
</pre>

<h3>Invalid recipients (to-cc-bcc)</h3>

<pre class="mid-pre">{
    "message": "error",
    "errors": [
        [
            "'INVALID_EMAIL' 'to' email not valid"
        ]
    ]
}
</pre>


<h3>Invalid Mime</h3>

<pre class="mid-pre">{
    "message": "error",
    "errors": {
        "message": "error",
        "errors": "Invalid Mime"
    }
}
</pre>

<h3>No enough credit in account subscription</h3>

<pre class="mid-pre">{
    "message": "error",
    "errors": {
        "message": "error",
        "errors": "nocredit"
    }
}
</pre>

<h3>deactivated account</h3>

<pre class="mid-pre">{
    "error": 3,
    "message": "Account for  test@domain.com  is inactive"
}
</pre>