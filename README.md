# Now Emails
Instantly deploy an email sending API to ZEIT Now

## Deployment

```
now -e AUTH_EMAIL=email@gmail.com AUTH_PASSWORD=supersecret tylersnyder/now-emails
```

By default, the API will use `Gmail` as the service provider. To use a different provider, specify a `SERVICE` as well:

```
now -e SERVICE_PROVIDER=Hotmail AUTH_EMAIL=email@hotmail.com AUTH_PASSWORD=supersecret tylersnyder/now-emails
```

To learn more about supported service providers, read more at [nodemailer.com](https://nodemailer.com/smtp/well-known/)

## Usage

Emails can be sent by making a `POST` request to your service. The body of this request should include:
```
{
  "to": "test@email.com",
  "subject": "sending emails",
  "text": "hello world!",
  "html": "hello <b>world</b>!",
  "from": "Myself <myself@domain.com>" // optional
}
```

You can specify only "text" or "html", or both. The "from" address is optional, but keep in mind Gmail does not allow you to overwrite the sender adress. Gmail will however use the display name, in this case `Myself`.