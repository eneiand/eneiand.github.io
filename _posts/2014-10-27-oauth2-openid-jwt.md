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

* Eran Hammer
  * hueniverse.com, lots of criticism of oauth
* Specification Bloat
  * too many alternative implementations to be a protocol
  * now a framework "The OAuth 2.0 Authorization Framework"
  * 6749, 6750, RFC 6819 -> Threat Model and Security Considerations
* Bearer Tokens
  * the token is not bound to the bearer
  * SSL required to securely transfer
  * if stolen then easy to impersonate
  * needs SSL checking
* Security Theater
  * the feeling of security
  * nobody stopping the client app spoofing the login
* Attack Surface
  * a big attack surface
  * who is the client
  * where to go to afterwards
  * scope, response_type etc.
  * lots of queries to manipulate and check for privileges
  * requires a lot of validation on the server, for clients, only particular redirects etc.
  * leastprivilege.com oauth2 problems and mitigations
  
#### Resources
