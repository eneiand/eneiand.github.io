#### The Security Stack for Modern Applications

#### JSON Web Tokens

#### Introduction to OAuth2

#### OAuth2 Flows

#### OpenID Connect

* OAuth2 os fpr de;egated authorization
* sometimes you just need authentication
* oauth2 is regularly abused for authentication
* abused like "if I can get an access token, then the user must be authenticated"
* malicious app steals token, uses it to impersonate user in legit app
* Open id connect built on top of oauth2
* adds an id token and userinfo endpoint
* openid.net/connect
* includes session management
* openid profile means access to profile
* client must validate the ID token is for this particular client, not stolen

#### OAuth2 Concerns

#### Resources
