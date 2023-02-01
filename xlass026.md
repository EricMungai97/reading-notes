# JSON Web Tokens

[Source](https://jwt.io/introduction/)

`JSON Web Token (JWT)` is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. 


This information can be `verified` and `trusted` because it is `digitally signed.`

JWTs can be signed using a secret `(with the HMAC algorithm)` or a public/private key pair using `RSA` or `ECDSA`.

Signed tokens can verify the integrity of the claims contained within it, while encrypted tokens hide those claims from other parties. 

## When you should use JSON Web Tokens

* Authorization - Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token
* Information Exchange - JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also `verify` that the content hasn't been `tampered` with.

## JSON Web Token Structure

It consists of three parts separated by dots

* Header
* Payload
* Signature

**Header**

consists of two parts: the `type of the token`, which is JWT, and the signing algorithm being used, such as `HMAC SHA256 or RSA`.

```
{
  "alg": "HS256",
  "typ": "JWT"
}
```
The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

**Payload**

Contains the `claims`. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: `registered`, `public`, and `private claims`.

1. Registered claims - These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others.

2. Public claims -  These can be defined at will by those using JWTs

3. Private  - These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

**Signature**

Created by taking the encoded header, the encoded payload, a secret, the algorithm specified in the header and signing that.

Example

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

The signature is used to verify the message wasn't changed along the way, and, in the case of tokens signed with a private key, it can also verify that the sender of the JWT is who it says it is.

## How JSON Web Tokens Work

When the user successfully logs in using their credentials, a JWT will be returned

Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema.

The content of the header would look like the following:

```Authorization: Bearer <token>```

The server's protected routes will check for a valid JWT in the Authorization header, and if it's present, the user will be allowed to access protected resources. 

If the JWT contains the necessary data, the need to query the database for certain operations may be reduced, though this may not always be the case.

Note that if you send JWT tokens through HTTP headers, you should try to prevent them from getting too big. 

With signed Tokens all the information contained within the token is exposed to users or other parties, even though they are unable to change it.

Therefore, don't put secret information within the token

## Why we should use JSON Web Tokens

They are less verbal than XML, when it is encoded its size is also smaller. This makes JWT a good choice to be passed in HTML and HTTP environments.

 JWT and SAML tokens can use a public/private key pair in the form of a X.509 certificate for signing. 

JSON parsers are common in most programming languages because they map directly to objects. Conversely, XML doesn't have a natural document-to-object mapping. This makes it easier to work with JWT than SAML assertions.

JWT is used at internet scale because of the ease of client-side processing of the JSON Web Token on multiple platforms, especially mobile.

## DRF JWT Authentication

[source](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

**Installation aND Setup**

run `pip install djangorestframework_simplejwt`

inside settings.py put this lines of code

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

inside urls.py
```python
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

**Usage**

Firstly `authenticate` and `obtain the token`.

The end point is `/api/token/` and it only accepts POST requests.

Afterwards store the `access token` and the `refresh token` on the client side.

To access the protected views on the backend you should include the access token in the header of all requests.

Example
```http://127.0.0.1:8000/hello/ "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQ1MjI0MjAwLCJqdGkiOiJlMGQxZDY2MjE5ODc0ZTY3OWY0NjM0ZWU2NTQ2YTIwMCIsInVzZXJfaWQiOjF9.9eHat3CvRQYnb5EdcgYFzUyMobXzxlAVh_IAgqyvzCE"```

To get a new access token use the refresh token endpoint `/api/token/refresh/`

The refresh token is valid for the next 24 hours.

The refresh token is necessary to ensure that the user still has the correct permissions.

## Django Runserver is Not Your Production Server

[Source](https://vsupalov.com/django-runserver-in-production/)

`python manage.py runserver`is  built for development convenience, but it’s not meant to be used as part of a production setup.

A server started with runserver is not guaranteed to be performant (it’s very slow), and it hasn’t been built with security concerns in mind. 

`WSGI` is a specification which people agreed on, which describes how an application server gets requests and uses them to construct Python Objects which are usable by Django.

Your Django app does not actually run as you would think a server would - waiting for requests and reacting to them. 

Your project provides a `uwsgi.py file`, which contains a function to be called by the application server. This function gets a Python object representing the incoming request.

This function calls your code, and produces a response object which is passed to the WSGI server. There the response is translated into a HTTP response and is passed back to the web server, which finally delivers it to the user.

If you want to run Django in production, be sure to use a production-ready web server like `Nginx`, and let your app be handled by a WSGI application server like `Gunicorn`.

## Things I want to know more about

WSGI, Gunicorn