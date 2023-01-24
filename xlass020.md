# Django Models

[source](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

Django web applications access and manage data through Python objects referred to as `models`.

***Models*** define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms,

Models are usually defined in an application's ***models.py file.*** 

```
from django.db import models
from django.urls import reverse

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    # …

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the URL to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name

```

A model can have an arbitrary number of `fields`, of any type — each one represents a column of data that we want to store in one of our database tables.

**common field arguments**

* help text
* verbose name
* default
* null
* blank
* choices
* primary key

**common field types**

* `Charfield` - is used to define short-to-mid sized fixed-length strings.

* `TextField` - s used for large arbitrary-length strings.

* `IntegerField` - a field for storing integer (whole number) values, and for validating entered values as integers in forms.

* `DatField` - used for storing/representing dates and date/time information (as Python datetime.date and datetime.datetime objects, respectively)

* `EmailField` - is used to store and validate email addresses.

* `ForeignKey` - is used to specify a one-to-many relationship to another database model (e.g. a car has one manufacturer, but a manufacturer can make many cars)

You can declare model-level metadata for your Model by declaring class Meta, as shown.

```
class Meta:
    ordering = ['-my_field_name']

```

One of the most useful features of this metadata is to `control the default ordering of records` returned when you query the model type

A model can also have `methods`

***Minimally, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.***

Another common method to include in Django models is `get_absolute_url()`, which returns a URL for displaying individual model records on the website

Once you've defined your model classes you can use them to create, update, or delete records, and to run queries to get all records or particular subsets of records.

To create a record you can define an instance of the model and then call `save()`.

```
# Create a new record using the model's constructor.
record = MyModelName(my_field_name="Instance #1")

# Save the object into the database.
record.save()

```

You can access the fields in this new record using the `dot syntax`, and change the values. You have to call save() to store modified values to the database.

```python
# Access model field values using Python attributes.
print(record.id) # should return 1 for the first record.
print(record.my_field_name) # should print 'Instance #1'

# Change record by modifying the fields, then calling save().
record.my_field_name = "New Instance Name"
record.save()

```

You can search for records that match certain criteria using the model's objects attribute (provided by the base class).

We can get all records for a model as a QuerySet, using `objects.all()`. The QuerySet is an iterable object, meaning that it contains a number of objects that we can iterate/loop through.

```python
all_books = Book.objects.all()

```

Django's filter() method allows us to filter the returned QuerySet to match a specified text or numeric field against particular criteria.

```python
wild_books = Book.objects.filter(title__contains='wild')
number_wild_books = wild_books.count()

```

## Things I want to know more about

How Models connect with the database