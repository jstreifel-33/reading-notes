# Django: Models and Admin

## Using Models

Source: [MDN - Django Tutorial pt. 3](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

Django web apps use models for accessing and managing data. Models determine the structure of stored data. Once your models are setup, Django will handle talking with whatever database you've chosen to use.

### Model Definition

Models are deinfed in `models.py`, as subclasses of `django.models.Model`.

```python
# MDN Example:

from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
```

### Fields

Models can have any number of fields, which represent a column of data to store in our database.

Fields are defined using functions from the models class, such as `models.CharField()`. Commonly used field types include:

* CharField
* TextField
* IntegerField
* DateField & DateTimeField
* EmailField
* FileField & ImageField
* AutoField
* ForeignKey
* ManyToManyField

### Metadata

Model-level metadata can be created using `class Meta`. This allows for many useful set-up features, such as defining the order to return query results in, or assigning a verbose name to a model.

### Methods

Models can have methods!

At a minimum, it is strongly recommended to define a `__str__()` method so that your model can be interpreted as a human-readable string.

`get_absolute_url()` is another common method added to models.

### Model Management

Records can be created using the save() method. Values can be accessed and modified using dot notation.

```python
#From MDN:
# Create a new record using the model's constructor.
record = MyModelName(my_field_name="Instance #1")

# Save the object into the database.
record.save()

# Access model field values using Python attributes.
print(record.id) # should return 1 for the first record.
print(record.my_field_name) # should print 'Instance #1'

# Change record by modifying the fields, then calling save().
record.my_field_name = "New Instance Name"
record.save()
```

### Searching for Records

We can retrieve all records of a model using `.objects.all()`. This returns an iterable QuerySet object.

`filter()` can be used to filter a QuerySet, matching text or numeric fields against criteria.

## Django Admin Site

Source: [MDN - Django Tutorial pt. 4](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)

Django includes a built-in admin application that allows for easy manipulation of records based on defined models.

To use the admin tools for record management, models must be registered and a "superuser" will need to be created to logging into the Django admin tools.

### Registering Models

In `admin.py` models can registered using `admin.site.register(ModelName)`

```python
# MDN Example:

from django.contrib import admin

# Register your models here.
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```

### Creating a Superuser

To create a super user, run the command `python manage.py. createsuperuser` in the terminal. This will prompt for a username, email address, and password.

Once complete, the superuser is created. Restart the development server and login at 127.0.0.8000/admin to get started with admin tools.

## Additional Resources

A Complete Beginner's Guide to Django, [Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html) and [Part 2](https://simpleisbetterthancomplex.com/series/2017/09/11/a-complete-beginners-guide-to-django-part-2.html)