# Authentication & Production Server

## JSON Web Tokens

Source: [jst.io - Into to JSON Web Tokens](https://jwt.io/introduction/)

JSON Web Token (JWT) is an open standard for secure transmissions between parities using a JSON object. They can be signed using a secret (HMAC) or public/private key system (RSA / ECDSA).

### When to Use JWT

* **Authorization** - The most common scenario. After logging in, requests from a user will include the JWT. Single Sign On widely uses JWT in most places.
* **Information Exchange** - Secure transmission of information between parties. Can verify sender identities and that data hasn't been tampered in transmission.

### JWT Structure

There are 3 parts to a JWT, separated by dots (.):

* **Header** - Defines the type of token and signing algorithm
* **Payload** - Contains claims and additional data. There are 3 types of claims:
  * Registered claims - predefined claims that provide useful information
  * Public claims - Defined at will, should be defined in IANA JSON Web Token Registry or as a URI to avoid collisions
  * Private claims - Custom claims to share information between parties
* **Signature** - result of signing using the **encoded header**, **encoded payload**, a **secret**, and the **algorithm** specified in the header. Used to verify no changes were made during transmission, and can be used to verify sender identity.

The output of parts is three Base64-URL strings separated by dots.

### How Do They Work?

Upon authentication a JWT is returned, which is sent back by the user when accessing protected routes or resources. This is usually done in the Authorization header with the Bearer schema.

**NOTE**: Secret information should not be placed within a token, since it is exposed to users and other parties.

## DRF JWT Authentication

Source: [SimpleIsBetterThanComplex - JWT Authentication in Django REST Framework](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

When logging in, a username and password are exchanged for an **access token** and **refresh token**.

Access tokens are short-lived.

Refresh Tokens live longer. Then they expire a fill login will be required again.

The use of two tokens is a security feature, since access tokens are created using a **secret key**.

### Using JWT In DRF

Getting setup with the djangorestframework_simplejwt library:

```Python
# $ pip install djangorestframework_simplejwt

# settings.py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}

#urls.py
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

First you'll need to authenticate and obtain a token, using the `api/token/` path from setting up.

`$ http post http://127.0.0.1:8000/api/token/ username=vitor password=123`

This will return an access and refresh token, which can be stored in local storage.

To access protected views, include the access token in a request header. It will be valid for **5 minutes**.

To get a new access token, use the refresh token on the refresh endpoint `/api/token/refresh/`.

`$ http post http://127.0.0.1:8000/api/token/refresh/ refresh=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU0NTMwODIyMiwianRpIjoiNzAyOGFlNjc0ZTdjNDZlMDlmMzUwYjg3MjU1NGUxODQiLCJ1c2VyX2lkIjoxfQ.Md8AO3dDrQBvWYWeZsd_A1J39z6b6HEwWIUZ7ilOiPE`

This will return a new access token for making resuests to protected resources!

Nice.

## The Production Server

Source: [vsupalov.com - Django Runserver is Not Your Production Server](https://vsupalov.com/django-runserver-in-production/)

We've been using `python manage.py runserver` for running Django apps locally. Fine. Cool. But the docs have a caveat to that:

>DO NOT USE THIS SERVER IN A PRODUCTION SETTING. It has not gone through security audits or performance tests.

Huh.

### Introducing the Production Stack

A production setup is composed of multiple components which all do one thing really well.

Server requests should be handled by a **web server**. Nginx is an example.

If a request requires processing, the web server should pass it an **application server**. WSGI is a specification for application servers, and Gunicorn is an example of a WSGI server.

### Django and the Production Stack

Django projects include a uwsgi.py file, which includes a function to be called by the application server.

When called, a response object is created and passed to the WSGI server. This is translated to HTTP and passed back to the web server, which delivers it to the requesting user.

Because of all the moving parts, Django doesn't really run the way we imagine static or single page apps. The good news is Django handles the hard stuff, for the most part.

Thanks, Django.

## Additional Resources

* [Pretty Printed - JSON Web Tokens With DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)
* [Gunicorn](https://gunicorn.org/)
* [Real Python - Django Migrations: A Primer](https://realpython.com/django-migrations-a-primer/)
