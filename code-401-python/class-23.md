# Django Custom User

## The Custom User Model

Source: [learndjango.com - Custom User Model](https://learndjango.com/tutorials/django-custom-user-model)

Django includes a built in user model, but it is highly recommended that we **create our own user model** for real-world projects. Let's get into what that actually involves.

First, you'll want to start a Django project. Within the project create an `accounts` app, and add it to settings under `INSTALLED_APPS` and `AUTH_USER_MODEL`.

```python
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'accounts', # new
]
...
AUTH_USER_MODEL = 'accounts.CustomUser' # new
```

Within `accounts/models.py` create your custom user model.

Create a form with fields for creating/modifying your user model (this can be done within `accounts/forms.py`) and update admin.py accordingly:

```python
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)
```

Now make migrations and migrate! It may also be worth it to make superuser for accessing administrative tools.

After that, you can use your form and model to create views and templates for logging in, logging out, and signing up using your new custom user model!

Refer to the reading source for more information on templating this information, but it's about what you'd expect.

## DjangoX

Source: [github - djangoX](https://github.com/wsvincent/djangox)

DjangoX is a batteries-included Django starter project. It has everything you need to get a website up an running quickly, and is compatible for use with Pip, Pipevn, and Docker.

It features:

- Django 3.1 & Python 3.8
- User log in/out, sign up, and password reset via django-auth
- Static files configurable with Whitenoise
- Styling with Bootstrap v4
- Debugging with django-debug-toolbar
- DRY forms with django-crispy-forms

Cool stuff, check it out at the github link.

## Additional Resources

- [Creating a Custom User Model](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)
- [Abstract User, User Profiles, and Signals in Django](https://www.youtube.com/watch?v=EudKs1HPUfE)
- [Docs: Substituting a Custom User Model](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)
