# Getting Started with Okta IDaaS Provider

Okta is an Identity as a Service (IDaaS) Provider.

1. Sign-up for a Free Developer Account at [Okta](https://developer.okta.com).

  1. You will be given a developer preview URL at dev-XYZ.oktapreview.com.
  1. You will receive an email with a temporary one-time password.

1. Navigate to your developer preview URL and sign-in

  1. Change your password.
  1. Select a security question.
  1. Select a security photo.
  1. Create your admin account and you'll be navigated to your dashboard at dev-XYZ-admin.oktapreview.com/dev/console

1. Clone the ASP.NET Core Sample

  1. git clone git@github.com:oktadeveloper/okta-aspnetcore-mvc-example.git
  1. Open the solution in Visual Studio 2017 Community Edition.
  1. Debug the solution.
  1. In the output window the process will report the port it is listening on (copy this).

1. In the Okta Admin Dashboard

  1. Select Applications.
  1. Select Add Application.
  1. Select Web.
  1. Name = Okta ASP.NET Core Demo Web.
  1. Base URIs = http://localhost:1368
  1. Login Redirect URIs = http://localhost:1368/authorization-code/callback
  1. Leave the rest of the settings alone (for now).
  1. Copy the Client ID and Client Secret into the appsettings.json file

```json
"Okta": {
    "Authority": "https://dev-XYZ.oktapreview.com/oauth2/default",
    "ClientId": "YOUR_CLIENT_ID",
    "ClientSecret": "YOUR_CLIENT_SECRET"
}

```
  1. Select My claims.

[Reference](https://github.com/oktadeveloper/okta-aspnetcore-mvc-example)
