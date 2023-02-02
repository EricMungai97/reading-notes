# Django Settings Best Practices

[Source](https://djangostars.com/blog/configuring-django-settings-best-practices/)

## Why we need to manage django settings

Different environments - each environment can have its own settings.

Sensitive data - This data cannot be stored in VCS

Sharing settings between members - a general approach is needed to eliminate human error when working with settings.

Django settings are a Python code.

**settings_local.py**

The basic idea of this method is to extend all environment-specific settings in the `settings_local.py` file which is ignored by VCS.


```python
ALLOWED_HOSTS = ['example.com']
DEBUG = False
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}

...

from .settings_local import *
```
**Cons**

* settings_local.py is not in VCS, so you can lose some of your Django environment settings.

* The Django settings file is a Python code, so settings_local.py can have some non-obvious logic.

* You need to have settings_local.example (in VCS) to share the default Django configurations for developers.

## Separate settings file for each environment

This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.

In this case, there are multiple files from which projects on Django get settings, and you make a settings package with the following file structure:

```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

settings/local.py:

```
from .base import *


ALLOWED_HOSTS = ['localhost']
DEBUG = True
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'local_db',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```

To specify for a project you run which Django configuration to use, you need to set an additional parameter:

```
python manage.py runserver --settings=settings.local
```

**Pros**

1. All environments are in VCS.

2. It’s easy to share settings between developers.

**Cons**

1. You need to find a way to handle secret passwords and tokens.

2. “Inheritance” of settings can be hard to trace and maintain.

## Environment Variables

To solve the issue with sensitive data, you can use environment variables in Django.

```python
import os


SECRET_KEY = os.environ['SECRET_KEY']
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ['DATABASE_NAME'],
        'HOST': os.environ['DATABASE_HOST'],
        'PORT': int(os.environ['DATABASE_PORT']),
    }
```

This is the simplest example using Python `os.environ` and it has several issues:

1. You need to handle KeyError exceptions.

2. You need to convert types manually (see DATABASE_PORT usage).
To fix KeyError, you can write your own custom wrapper. For example:

```python
import os

from django.core.exceptions import ImproperlyConfigured


def get_env_value(env_variable):
    try:
      	return os.environ[env_variable]
    except KeyError:
        error_msg = 'Set the {} environment variable'.format(var_name)
        raise ImproperlyConfigured(error_msg)


SECRET_KEY = get_env_value('SECRET_KEY')
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': get_env_value('DATABASE_NAME'),
        'HOST': get_env_value('DATABASE_HOST'),
        'PORT': int(get_env_value('DATABASE_PORT')),
    }
}
```

**Pros**

1. Django config is separated from code.
2. Environment parity – you have the same code for all environments.
3. No inheritance in settings, and cleaner and more consistent code.
4. There is a theoretical grounding for using Django environment variables – 12 Factors.

**Cons**

 You need to handle sharing default config between developers.
 
## 12 Factors

A collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku.

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

Its main rule is `to store configuration in the environment`.

## Naming Conventions

1. Give meaningful names to your settings.

2. Always use the prefix with the project name for your custom (project) settings.

3. Write descriptions for your settings in comments.

## Django Settings: Best practices

1. Keep settings in environment variables.

2. Write default values for production configuration (excluding secret keys and tokens).
3. Don’t hardcode sensitive settings, and don’t put them in VCS.
4. Split settings into groups: Django, third-party, project.

5. Follow naming conventions for custom (project) settings.

## Things I want to Know More About

How to use environmental variables in python.