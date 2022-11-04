# What is OAuth

[SOURCE](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

***What is OAuth?***

It is an open -standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated  access to their assets without actually sharing the initial, related, single logon credential.

***Give an example of what using OAuth would look like.*** 

Trying to login in to a website and it gives the option to sign in using your google account.

***How does OAuth work? What are the steps that it takes to authenticate the user?***

1. The user initiates a transaction or feature that needs access to another unrelated site.

2. 1st website connects to the 2nd website on behalf of the user, using OAuth.

3. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

4. The first site gives this token and secret to the initiating user’s client software.

5. The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).

6. If not already authenticated to the authorization provider, the client may be asked to authenticate.

7. The user approves (or their software silently approves) a particular transaction type at the first website.

8. The user is given an approved access token (notice it’s no longer a request token).

9. The user gives the approved access token to the first website.

10. The first website gives the access token to the second website as proof of authentication on behalf of the user.

11. The second website lets the first website access their site on behalf of the user.

***What is OpenID?***

A single sign-in, vouching for  identities of users when logging in to multiple websites.

## Authorization and Authentication flows

[SOURCE](https://auth0.com/docs/get-started/authentication-and-authorization-flow)

***What is the difference between authorization and authentication?***

```Authentication``` is the process of a suer/subject proving its ownership of a presnted identity, by providing a password or some other uniquely owned or presented factor while ```authorization```  is the process of letting a subject access resources after a successful authentication, oftentimes somewhere else.

***What is Authorization Code Flow?***

It is the most flexible way to obtain access to protected resources like web API's.

***What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?***

***What is Implicit Flow with Form Post?***

Authorization process for apps that are unable to securely store client scerets.

***What is Client Credentials Flow?***

Flow that entails the system authenticating/ authorizing an app rather than the user.

***What is Device Authorization Flow?***

Authorization process that has the user go to a link on their computer or smartphone and authorize their device.

***What is Resource Owner Password Flow?***

Authorization process that requests that users provide credentials using an interactive form.
