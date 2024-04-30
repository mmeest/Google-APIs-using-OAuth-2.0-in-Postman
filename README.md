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

Select dropdown in the top navigation menu. Then click 'New Project' button.

Give your project a name, and select a location and an organization.
