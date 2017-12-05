# Getting Started with Okta IDaaS Provider

Okta is an Identity as a Service (IDaaS) Provider.

1. Sign-up for a Free Developer Account at [Okta](https://developer.okta.com).

* You will be given a developer preview URL at dev-XYZ.oktapreview.com.
* You will receive an email with a temporary one-time password.

1. Navigate to your developer preview URL and sign-in

* Change your password.
* Select a security question.
* Select a security photo.
* Create your admin account and you'll be navigated to your dashboard at dev-XYZ-admin.oktapreview.com/dev/console

1. Clone the ASP.NET Core Sample

* git clone git@github.com:oktadeveloper/okta-aspnetcore-mvc-example.git
* Open the solution in Visual Studio 2017 Community Edition.
* Debug the solution.
* In the output window the process will report the port it is listening on (copy this).

1. In the Okta Admin Dashboard

* Select Applications.
* Select Add Application.
* Select Web.
* Name = Okta ASP.NET Core Demo Web.
* Base URIs = http://localhost:1368
* Login Redirect URIs = http://localhost:1368/authorization-code/callback
* Leave the rest of the settings alone (for now).
* Copy the Client ID and Client Secret into the appsettings.json file

```json
"Okta": {
    "Authority": "https://dev-XYZ.oktapreview.com/oauth2/default",
    "ClientId": "YOUR_CLIENT_ID",
    "ClientSecret": "YOUR_CLIENT_SECRET"
}

```
* Select My claims.

[Reference](https://github.com/oktadeveloper/okta-aspnetcore-mvc-example)
