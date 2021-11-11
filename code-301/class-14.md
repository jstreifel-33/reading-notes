# Authentication

## What is OAuth

* What is OAuth?
  * OAuth is an open-standard authorization protocol. It allows multiple unrelated servers and services to use a single shared login without actually accessing or sharing secure information.
* Give an example of what using OAuth would look like.
  * OAuth is what allows us to log in to various different services using GitHub or Google as the authenticating account.
* How does OAuth work? What are the steps that it takes to authenticate the user?
  * The site requesting authorization reaches out to the authenticating service, has the user verify their identity, and receives a secret authorization token that proves the user's identity.
* What is OpenID?
  * OpenID is a different service, used for authentication. It's used for humans logging into machines, instead of machines logging into machines.

## Authorization and Authentication Flows

* What is the difference between authorization and authentication?
  * Authentication involves providing credentials, while authorization involves providing permission to act a verified by credentials.
* What is Authorization Code Flow?
  * A user goes to login on a service, Auth0 receives a request for authorization and presents the user with a login prompt. On successful login, a code is sent to the service, who returns the code with the associated client to authorize. Auth0 then generates a token and provides it to the web service, which acts the user's unique login to the service when communicating with the service's API.
* What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
  * PKCE is generally the same as before, but has an extra step between the app and Auth0 that involves a unique code challenge for verification between the app and Auth0. This ensures that data is flowing between the same client between authorization steps.
* What is Implicit Flow with Form Post?
  * Implicit flow with form post just retrieves a token from Auth0 without needing to maintain a sercret within the web app.
* What is Client Credentials Flow?
  * Client credential flow uses a service on the backend to authenticate an app rather than a user.
* What is Device Authorization Flow?
  * Device authorization flow authorizes a device instead of a user.
* What is Resource Owner Password Flow?
  * Resource owner password flow requests a users credentials for authorization. It is generally not recommended that this flow be used.

## Things I want to know more about

Really this seems like a lot to take in. I guess what I'd like to know is when to use what kind of Auth0 flow.
