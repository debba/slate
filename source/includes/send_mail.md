
# Send email

## Send email

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
