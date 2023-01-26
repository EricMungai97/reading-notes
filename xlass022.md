# Django Custom User Model

For a real world project Official Django documentation highly recommends using a custom user model instead.

## AbstractUser vs AbstractBaseUser

There are two modern ways to create a custom user model in Django: 
1. AbstractUser
2. AbstractBaseUser.

`AbstractBaseUser` requires much more work.

The `AbstractUser` subclasses `AbstractBaseUser` but provides more default configuration.

## Creating Custom User Model

Creating our initial custom user model requires four steps:

* update django_project/settings.py
* create a new CustomUser model
* create new UserCreation and UserChangeForm
* update the admin

In `settings.py` we add our `app` and use the `AUTH_USER_MODEL` config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser.

Within INSTALLED_APPS add app at the bottom. Then at the bottom of the entire file, add the AUTH_USER_MODEL = `nameofapp.CustomUser`

We then update `app/models.py` with a new User model which we'll call `CustomUser`.

```python
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

We need new versions of two form methods that receive heavy use working with users. Create a new file in the app called `forms.py.`

```python
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

Finally we update `admin.py` since the Admin is highly coupled to the default User model.

```python
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

We can now run `makemigration`s and `migrate` for the first time to create a new database that uses the custom user model.

We then create a superuser we can use to log in to the admin and test out log in/log out. 

## Things I want to know more about

AbstractBaseUser