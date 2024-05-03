<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/API.png" width="300px">
  </p>
</div>


# Google-APIs-using-OAuth-2.0-in-Postman
Google APIs using OAuth 2.0 in Postman


# Contents
* [Tasks](#tasks)
* [Setting up environment](#setting-up-environment)
* [Solution](#solution)


<hr>


## Tasks

**1. Prepare a google sheet for the project:**

* Create google sheet, manually, under your normal google account
* Fill in, manually, 3 columns: Name, email and Age (Cells A1 => C1)
* Add minimum 5 rows of data in the excel sheet
* Make a GET request in Postman to https://sheets.googleapis.com/v4/spreadsheets/{{sheet_id}}/values/A1:C100

**2. Read the sheet's header row:**

* In the tests tab, parse the jsonData to get the details of first row ONLY. This shall be in a hardcoded “array index [0]”.
* Print the result to the console
* Does the result show your Header row “A1:C1”?

**3. Print data in a CSV format:**

* Make a for loop on the array of rows to print out their values in the Console, the output shall look like this:

```
Name,email,Age
John,xy@email.com,15
Doe,ab@email.com,24
Malcom,xa@email.com,35
```

* Remember, such format is “tailored” which means you have to convert the array into your own print message. This means you will need
to work with a for loop.
* For a successful for loop, you will need to determine the length of the array first (i.e. count the array items before running the loop)

**Bonus Task:**

* Update your print message to print only the first column.
* To understand this better, you will need to study again the JSON response. Maybe you'll need to read about nested arrays as well.
* The output shall look like this:

```
Name
John
Doe
Malcom
```

Now that you are comfortable with Postman API and parsing its data, what other requests can you make? study the API and feel free to
try out more functionalities.

Remember, you have access now to Google Sheets API as a developer, which means you can POST, UPDATE and DELETE sheets and
their contents.
Best of luck!


<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/oauht2.png" width="220px">
  </p>
</div>


## Setting up environment


https://blog.postman.com/how-to-access-google-apis-using-oauth-in-postman/

OAuth Playground on Google Devleopers:

https://developers.google.com/oauthplayground/

Authenticating with OAuth 2.0

https://learning.postman.com/docs/sending-requests/authorization/oauth-20/

Google Sheets API 

https://developers.google.com/sheets/api/reference/rest

Google Sheet operations

https://developers.google.com/sheets/api/samples/sheet

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
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(1).png" width="700px">
  </p>
</div>

Click 'New Project' button.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(2).png" width="700px">
  </p>
</div>

Give your project a name, and select a location and an organization.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(3).png" width="700px">
  </p>
</div>

On notification modal click 'SELECT PROJECT'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(4).png" width="700px">
  </p>
</div>

On top left corner select hamburger menu and 'VIEW ALL PRODUCTS'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(5).png" width="700px">
  </p>
</div>

Next select 'Apis and services'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(6).png" width="700px">
  </p>
</div>

Select 'Library'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(7).png" width="700px">
  </p>
</div>

Select 'Google Sheets API'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(8).png" width="700px">
  </p>
</div>

Click on 'ENABLE'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/A%20(9).png" width="700px">
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

3. Authorize with Postman

Navigate to: https://sheets.new/
and create new Google sheet. Give it a name and populate with random data.

Create Postman collection and add new POST request:
https://sheets.googleapis.com/v4/spreadsheets

Copy from your newly created Google spreadsheet URL id of your document.
It is located right after: https://docs.google.com/spreadsheets/d/...

Copy this id to your Postman POST request and send it.

You will get unauthorized 401 error.

Navigate to Authorization and select OAuth 2.0

Scroll down to 'Configure New Token'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(6).png" width="700px">
  </p>
</div>

* Grant Type: 'Authorization Code'
* Callback URL: this is automatically set
* Auth URL: https://accounts.google.com/o/oauth2/v2/auth?access_type=offline
* Access Token URL: https://oauth2.googleapis.com/token
* Client ID: ID that was generated by Google Cloud Console. Store it in variable 'ClientID' and use it as {{ClientID}}
* Client Secret: Secret that was generated by Google Cloud Console. Store it in variable 'ClientSecret' and use it as {{ClientSecret}}
* Scope: https://spreadsheets.google.com/feeds/

Click on 'Get New Access Token' button.

---

NB! Check your creditentials if it fetching token times out. Your user id may have extra empty space at the end!!

---

You may get following Error:

```
Error: Could not complete OAuth 2.0 token request
```

Solution:
Check that you have right 'Access Token URL'

```
https://oauth2.googleapis.com/token
```

---

When sending request from Postman you may get 400 error invalid_request. 

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/d%20(1).png" width="700px">
  </p>
</div>

Reason may be that Postman did'nt fetch right URI from Google Cloud.
To resolve it check 'Authorize using browser' box.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/d%20(2).png" width="700px">
  </p>
</div>

---

You may also get a following error after validating with Google account:

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(1).png" width="700px">
  </p>
</div>

That means you don't have test user validated.
To resolve this navigate to Google Console: https://console.cloud.google.com/
And select 'APIs and Services'

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(2).png" width="700px">
  </p>
</div>

On left menu select 'OAuth consent screen' 

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(3).png" width="700px">
  </p>
</div>

Scroll down and select 'Add users' button under Test users

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(4).png" width="700px">
  </p>
</div>

Type your google account e-mail and click save.
Problem should be resolved.

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/c%20(5).png" width="700px">
  </p>
</div>

Now you should be able to get access token by validating your Google account. 

After validating popup window should redirect you back to Postman. NB! Pop up windows should be allowed in browser to succeed!

Back in Postman new modal window should pop up with new Access Token.


4. Managing tokens

You can generate new tokens after expiration by following the same process we discussed above, but you won’t have to go through every step again. If you have a token added, you can manage all your tokens. In the Authorization tab, click on the token list option and select Manage Tokens. Here, you can see a list of added tokens, alongside their validity. You can choose to delete any tokens that you no longer need.

5. Revoking access

   You can navigate to https://myaccount.google.com/permissions to see a list of all third-party applications that have access to your account. You can then choose to revoke authorization access to any of these applications by clicking Remove access. In our case, the application to look for is called “Postman x Google.”



## Solution   

1. Following sheet created at Google Docs:

<div>
  <p align="center">
    <img src="https://github.com/mmeest/Google-APIs-using-OAuth-2.0-in-Postman/blob/main/img/d%20(3).png" width="700px">
  </p>
</div>

Sending GET request:

```
https://sheets.googleapis.com/v4/spreadsheets/{{SheetID}}/values/A1:C100
```

JSON response:

```
{
    "range": "OAuthTest!A1:C100",
    "majorDimension": "ROWS",
    "values": [
        [
            "Name",
            "email",
            "Age"
        ],
        [
            "Victor",
            "victor@gmail.it",
            "31"
        ],
        [
            "Oscar",
            "oscar.oscar@unknown.com",
            "42"
        ],
        [
            "Brandon",
            "brandon.2@gmail.com",
            "11"
        ],
        [
            "Emil",
            "emil.999@fb.com",
            "41"
        ],
        [
            "George",
            "georgegeorge@google.com",
            "42"
        ],
        [
            "Daniel",
            "daniel005@mail.com",
            "52"
        ],
        [
            "Richard",
            "richard@gmail.com",
            "22"
        ],
        [
            "William",
            "william.doe@yahoo.com",
            "27"
        ]
    ]
}
```

2. Reading first row of the document:

   Solution A

   Sending GET request to fetch first row:

```
https://sheets.googleapis.com/v4/spreadsheets/{{SheetID}}/values/A1:C1
```

And script for displaying it in console:

```
const jsonData = pm.response.json();

console.log('' + jsonData.values);
```

Result:

```
Name,email,Age
```

---

  Solution B

  Getting all rows and parsing first one.
  Request UR (where 'OAuthTest' is the name of the current sheet)L:

```
https://sheets.googleapis.com/v4/spreadsheets/{{SheetID}}/values/OAuthTest
```

Script:

```
const jsonData = pm.response.json();

console.log('' + jsonData.values[0]);
```

Result:

```
Name,email,Age
```

---

Tests for GET request:

```
const jsonData = pm.response.json();

pm.test("Correct response code is returned", function () {
    pm.expect(pm.response.code).to.equal(200);
});

pm.test("Check correct number of rows - 9", function () {
    var responseJSON = pm.response.json();
    pm.expect(responseJSON).to.be.an('object');
    pm.expect(responseJSON.values).to.be.an('array').that.has.lengthOf(9);
});
```

3. Printing out data in CSV format:

Sending GET request to:

```
https://sheets.googleapis.com/v4/spreadsheets/{{SheetID}}/values/OAuthTest
```

Script:

```
const jsonData = pm.response.json();

// storing how many rows current document has into variable
let numOfRows = Object.keys(jsonData.values).length;

for(let i = 0; i < numOfRows; i++){
        console.log("" + jsonData.values[i]);
}
```

Output to console:

``` 
Name,email,Age 
Victor,victor@gmail.it,31 
Oscar,oscar.oscar@unknown.com,42 
Brandon,brandon.2@gmail.com,11 
Emil,emil.999@fb.com,41 
George,georgegeorge@google.com,42 
Daniel,daniel005@mail.com,52 
Richard,richard@gmail.com,22 
William,william.doe@yahoo.com,27
```

Bonus Task to print out first column

Once again send following GET request

```
https://sheets.googleapis.com/v4/spreadsheets/{{SheetID}}/values/OAuthTest
```

Script:

```
const jsonData = pm.response.json();

// storing how many rows current document has into variable
let numOfRows = Object.keys(jsonData.values).length;

// printing ony first column: [0]
for(let i = 0; i < numOfRows; i++){
        console.log(jsonData.values[i][0]);
}
```

Output in console:

``` 
Name 
Victor 
Oscar 
Brandon 
Emil 
George 
Daniel 
Richard 
William
```
