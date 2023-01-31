# Permissions and Postgressql

[source](https://www.django-rest-framework.org/api-guide/permissions/)

Together with `authentication` and `throttling`, permissions determine whether a request should be granted or denied access.

Permissions are used to grant or deny access for different classes of users to different parts of the API.

The `IsAuthenticated` class in REST framework allows access to any authenticated user and denies access to any unauthenticated user.

`IsAuthenticatedOrReadOnly` class allows full access to authenticated users, but allow read-only access to unauthenticated users.

If any permission check fails, an `exceptions.PermissionDenied` or exceptions.`NotAuthenticated exception` will be raised, and the main body of the view will not run.

## Object level Permissions

Object level permissions are used to determine if a user should be allowed to act on a particular object, which will be typically be a model instance.

They are usually run by REST framework's generic views when `.get_object()` is called.

If you are writing your own views and want to enforce object level permissions  you'll need to explicitly call the `..check_object_permissions(request, obj)` method on the view at the point at which you retrieved the object.

**Limitations of object level permissions**

* The generic views cannot automatically apply object level permissions to each instance in a queryset when returning a list of objects.

* When used you'll want to `filter the queryset` appropriately, to ensure that users only have visibility onto instances that they are permitted to view.

## Settings the permission policy

Globally
```python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

 authentication policy on a per-view, or per-viewset basis, using the APIView class-based views.
 
```python
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

## API Reference

`AllowAny` permissions class will allow unrestricted access.

`IsAdminUser` will deny permission to any user, unless `user.is_staff` is True in which case permission will be allowed.

## DjangoModelPermissions

1. POST requests require the user to have the `add` permission on the model.
2. PUT and PATCH requests require the user to have the `change` permission on the model.
3. DELETE requests require the user to have the `delete` permission on the model.

## Custom permissions

To implement custom permissions we override `BasePermission` and implement either, or both, of the following methods:

* `.has_permission(self, request, view)`
* `.has_object_permission(self, request, view, obj)`

The methods should return `True` if the request should be granted access, and `False` otherwise.

**Overview of access restriction methods**

`queryset/get_queryset()`: Limits the general visibility of existing objects from the database. The queryset limits which objects will be listed and which objects can be modified or deleted.

`serializer_class/get_serializer()`: Instance level restrictions that apply to all objects on input and output. The serializer may have access to the request context. The `get_serializer()` method can apply different serializers based on the current action.

## Third party packages

* DRF - Access Policy -  provides a way to define complex access rules in declarative policy classes that are attached to view sets or function-based views. The policies are defined in JSON in a format similar to AWS' Identity & Access Management policies.

* Composed Permissions - provides a simple way to define complex and multi-depth (with logic operators) permission objects, using small and reusable components.

* REST Condition -  another extension for building complex permissions in a simple and convenient way. The extension allows you to combine permissions with logical operators.

* DRY Rest Permissions - provides the ability to define different permissions for individual default and custom actions.

* Django Rest Framework Roles

* Django REST Framework API Key - provides permissions classes, models and helpers to add API key authorization to your API

* Django REST Framework Role Filters
