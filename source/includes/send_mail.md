
# Send email

## Send email V2

> Request Body Example

```json

{
	"from": "email address",
	"to": "recipient email address",
	"subject": "subject in string format",
	"content": "plain / text content",
	"html_content": "html content",
	"attachments": [
		{
			"name": "test.gif",
			"type": "image/gif",
			"content": "The Base64 encoded content of the attachment."
		},
{
			"name": "test.pdf",
			"type": "application/pdf",
			"content": "The Base64 encoded content of the attachment."
		}
	]
}


```

> Attachment object

```json
{
  "content": "The Base64 encoded content of the attachment.",
  "name": "The filename of the attachment.", 
  "type": "The mime type of the content you are attaching. For example, image/gif."
}
```

> Request headers:

```
Content-Type: application/json; charset=utf-8
```

> Response headers:

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

> Response body (Turbo-SMTP successfully received your message):

```json
 { 
   "message":"OK" 
 }

```

> Response body Example (in case of error):
 

```json
 { 
     "message": "error",
     "errors": [
        "error message"
     ]
 } 
```

### Request endpoint:

`POST https://api.eu.turbo-smtp.com/api/v2/mail/send` --> for **EU** users

`POST https://api.turbo-smtp.com/api/v2/mail/send` --> for **NON EU** users

- `authuser` is the email of turboSMTP account (this param can be used as POST or Headers)
- `authpass` is the password of turboSMTP account (this param can be used as POST or Headers)
- `from` is the from address
- `to` is provided as comma-separated recipients list
- `subject` is the subject of the email (optional)
- `cc` is provided as comma-separated copy list (optional)
- `bcc` is provided as comma-separated hidden copy list (optional)
- `content` is the text content of the email (optional)
- `html_content` is the html content of the email (optional)
- `custom_headers` are additional headers, e.g. `{"X-key1":"value1", "X-key2":"value2"}` (optional)
- `mime_raw` mime message which replaces `content` and `html_content`
- `attachments` array of attachment objects

### Attachments

It should be configured as an array of attachments.

####Limitations

- The total size of your email, including attachments, must be less than 24MB.
    
Failed requests will always return an error response, including a response code and a message explaining the reason for the error.

Response Code | Response Message | Description
------------- | ------             | ---------------------
200           |  OK                | Turbo-SMTP successfully received your message 
400           | BAD REQUEST        | Something wrong with the request body/parameters
401           | UNAUTHORIZED       | Wrong credentials
500           | SERVER_UNAVAILABLE | An error occurred on a Turbo-Smtp server.

<h3>Errors</h3>
<p>Please check <a href="#send-api-errors">Errors section</a> for a detailed errors documentation.</p>

### Some implementations

PHP: [Download PHP sample code](https://dashboard.serversmtp.com/downloads/turbo_send_email_code_v2.zip "Go to PHP implementation")

C#: [Download C# sample code](https://dashboard.serversmtp.com/downloads/CSharp-turboSMTP-API_v2.zip "Go to C# implementation")

Java: [Download Java sample code](https://dashboard.serversmtp.com/downloads/Java-turboSMTP-API_v2.zip "Go to Java implementation")

Python: [Download Python sample code](https://dashboard.serversmtp.com/downloads/Python-turboSMTP-API_v2.zip "Go to Python implementation")

Perl: [Download Perl sample code](https://dashboard.serversmtp.com/downloads/Perl-turboSMTP-API_v2.zip "Go to Perl implementation")

Ruby: [Download Ruby sample code](https://dashboard.serversmtp.com/downloads/Ruby-turboSMTP-API_v2.zip "Go to Ruby implementation")


## Send email V1  <span class = "deprecated">deprecated</span>
<span class = "deprecated">This endpoint is deprecated and will stop working on June 30th, 2021</span>

<h3>Migration instructions</h3>
<ol>
<li> Change the API url from <code>https://api.turbo-smtp.com/api/mail/send</code> to:<br>
   <code>https://api.turbo-smtp.com/api/v2/mail/send</code> (NON EU users)<br>
   or<br>
   <code>https://api.eu.turbo-smtp.com/api/v2/mail/send</code> (EU users)</li>
<li>Handle all types of status codes and status messages refer to <a href="#send-email-v2">Send API v2</a></li>
</ol>

> Request Body Example

```json

{
	"from": "email address",
	"to": "recipient email address",
	"subject": "subject in string format",
	"content": "plain / text content",
	"html_content": "html content",
	"attachments": [
		{
			"name": "test.gif",
			"type": "image/gif",
			"content": "The Base64 encoded content of the attachment."
		},
{
			"name": "test.pdf",
			"type": "application/pdf",
			"content": "The Base64 encoded content of the attachment."
		}
	]
}


```

> Attachment object

```json
{
  "content": "The Base64 encoded content of the attachment.",
  "name": "The filename of the attachment.", 
  "type": "The mime type of the content you are attaching. For example, image/gif."
}
```

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
   "message":"OK" 
 }

```

> Response body (in case of error):

```json
 { 
     "message": "error",
     "errors": [
        "error message"
     ]
 } 
```

### Request endpoint:

`
POST https://api.turbo-smtp.com/api/mail/send
`

- `authuser` is the email of turboSMTP account (this param can be used as POST or GET)
- `authpass` is the password of turboSMTP account (this param can be used as POST or GET)
- `from` is the from address
- `to` is provided as comma-separated recipients list
- `subject` is the subject of the email (optional)
- `cc` is provided as comma-separated copy list (optional)
- `bcc` is provided as comma-separated hidden copy list (optional)
- `content` is the text content of the email (optional)
- `html_content` is the html content of the email (optional)
- `custom_headers` are additional headers, e.g. `{"X-key1":"value1", "X-key2":"value2"}` (optional)
- `mime_raw` mime message which replaces `content` and `html_content`
- `attachments` array of attachment objects

### Attachments

It should be configured as an array of attachments.

####Limitations

- The total size of your email, including attachments, must be less than 4MB.
    
### Some implementations

PHP: [Download PHP sample code](https://dashboard.serversmtp.com/downloads/turbo_send_email_code.zip "Go to PHP implementation")

C#: [Download C# sample code](https://dashboard.serversmtp.com/downloads/CSharp-turboSMTP-API.zip "Go to C# implementation")

Java: [Download Java sample code](https://dashboard.serversmtp.com/downloads/Java-turboSMTP-API.zip "Go to Java implementation")

Python: [Download Python sample code](https://dashboard.serversmtp.com/downloads/Python-turboSMTP-API.zip "Go to Python implementation")

Perl: [Download Perl sample code](https://dashboard.serversmtp.com/downloads/Perl-turboSMTP-API.zip "Go to Perl implementation")

Ruby: [Download Ruby sample code](https://dashboard.serversmtp.com/downloads/Ruby-turboSMTP-API.zip "Go to Ruby implementation")
