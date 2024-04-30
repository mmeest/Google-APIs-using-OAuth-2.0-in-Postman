# Google-APIs-using-OAuth-2.0-in-Postman
Google APIs using OAuth 2.0 in Postman

https://blog.postman.com/how-to-access-google-apis-using-oauth-in-postman/

OAuth 2.0 - Authorization Framework

OAuth provides standardized and secure protocol for authorization between APIs and third-party
applications that doesn't require users to share credentials. It also allows an application to
tet user-consented access to specific data without requesting any confidential data (such as
passwords) from the user.

## Access and refresh tokens

An access token is an authorization string that is issued to a third-party application. These
tokens represent specific scopes that have been granted by the user or resource owner and are
often short-lived. Access tokens can be stored in different formats, the most common being the 
JWT - JSON Web Tokens.

Access tokens are short-lived. To obtain new access tokens refresh tokens can be used.

OAuth 2.0 spec.

* Resource owner: user who is granting access
* Resource server: server that is hosting protected resources
* Client: third-party application that is requesting access
* Authorization server: issues access tokens


## OAuth 2.0 worflow

1. Client gets a client ID and client secret from auth. server
2. Client requests authorization from the user / resource owner
3. User grants authorization to the client through the auth. server by logging in with creditentials
4. Client uses this authorization code to request the access token from endpoint
5. Auth. server generates an access token
6. Client sends the access token to the resource server to request access to resources
7. Resource server validates the access token with the auth. server and grants access


## Using Postman to access a Google API

1. Create and set up a new project

Navigate to Google Cloud Console: https://console.cloud.google.com/welcome?pli=1&project=skilled-curve-308614

Select dropdown in the top navigation menu. 

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(1).png" width="700px">
  </p>
</div>

Click 'New Project' button.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(2).png" width="700px">
  </p>
</div>

Give your project a name, and select a location and an organization.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(3).png" width="700px">
  </p>
</div>

On notification modal click 'SELECT PROJECT'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(4).png" width="700px">
  </p>
</div>

On top left corner select hamburger menu and 'VIEW ALL PRODUCTS'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(5).png" width="700px">
  </p>
</div>

Next select 'Apis and services'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(6).png" width="700px">
  </p>
</div>

Select 'Library'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(7).png" width="700px">
  </p>
</div>

Select 'Google Sheets API'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(8).png" width="700px">
  </p>
</div>

Click on 'ENABLE'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/A%20(9).png" width="700px">
  </p>
</div>

---

2. Get your creditentials

Click on 'CREATE CREDITENTIALS' button

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(1).png" width="700px">
  </p>
</div>

Google Sheets API should be autoselected. 
Select 'User data' for accessing. And click Next

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(2).png" width="700px">
  </p>
</div>

Give your app a name and contact e-mail address.

NB! When naming your app don't use 'Google' in it or you will get an error:
```
An error saving your app has occurred
The request has been classified as abusive and was not allowed to proceed
```

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(3).png" width="700px">
  </p>
</div>

Click 'ADD OR REMOVE SCOPES'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(4).png" width="700px">
  </p>
</div>

Select 'Google Sheets API' .../auth/spreadsheets.readonly and click 'Update'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(5).png" width="700px">
  </p>
</div>

Under 'Oauth Client ID' select application type 'Web Application' and give a client name:

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(6).png" width="700px">
  </p>
</div>

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(7).png" width="700px">
  </p>
</div>

Under authorized URI's add URI. 
If using Postman web client add: https://oauth.pstmn.io/v1/browser-callback
If using Postman desktop client add. https://oauth.pstmn.io/v1/callback
If you are using both clients add both URIs.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(8).png" width="700px">
  </p>
</div>

Copy client ID and download your creditentials

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(19).png" width="700px">
  </p>
</div>

Navigate to your newly created creditentials

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(10).png" width="700px">
  </p>
</div>

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/B%20(11).png" width="700px">
  </p>
</div>







