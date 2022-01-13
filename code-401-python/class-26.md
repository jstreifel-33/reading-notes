# Permissions & Postgresql

Source: [django-rest-framework.org](https://www.django-rest-framework.org/api-guide/permissions/)

Permission checks determine if requests are allowed to proceed. Information checked is usually in `request.user` or `request.auth`.

The simplest permission allows any authenticated user to make requests, corresponding to the `IsAuthenticated` class of REST framework.

Alternatively `IsAuthenticatedOrReadOnly` gives read permission to unauthenticated users.

## Determining Permissions

Permissions are defined as a list of permission classes. When permission checks fail a 403 or 401 response is returned, according to certain rules:

* Request authenticated, but permission denied - 403
* Request not authenticated, and highest priority authentication class **does not use** `WWW-Authenticate` headers - 403
* Request not authenticated, and highest priority authentication class **does use** `WWW-Authenticate` headers - 401

## Object Level Permissions

Object-level permissions determine if a user can act on a particular object, usually a model instance.

They are run when `.get_object()` is called.

## Setting Permission Policy

Default permission class may be set globally in settings:

```Python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

Or on a per-view or per-viewset basis:

```Python
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)
```

## Access Restriction Methods

* `queryset`/`get_queryset()` - Limits general visibility of existing db objects.
* `permission_classes`/`get_permissions()` - General permission checks for an action, request, or object.
* `serializer_class`/`get_serializer` - Instance level restrictions to all object on input and output.

## Additional Resources

* [Classy Django REST](https://www.cdrf.co/)
* [DRF - Generic Views](https://www.django-rest-framework.org/api-guide/generic-views/)
