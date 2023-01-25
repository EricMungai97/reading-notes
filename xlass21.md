# Django Forms

`Forms` are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on. 

**Process flowchart of how Django handles form requests**

![Process flowchart](/images/form_handling_-_standard.png)

The main things that Django's form handling does are:

1. Display the default form the first time it is requested by the user. 
2. Receive data from a submit request and bind it to the form
3. Clean and validate the data. 
4. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
5. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
6. Once all actions are complete, redirect the user to another page.

## Form

The `Form class` is the heart of Django's form handling system. It specifies the fields in the form, their layout, display widgets, labels, initial values, valid values, and (once validated) the error messages associated with invalid fields. The class also provides methods for rendering itself in templates using predefined formats (tables, lists, etc.) or for getting the value of any element (enabling fine-grained manual rendering).

**Declaring a Form**

The declaration syntax for a Form is very similar to that for declaring a Model, and shares the same field types (and some similar parameters). This makes sense because in both cases we need to ensure that each field handles the right types of data, is constrained to valid data, and has a description for display/documentation.

```python
from django import forms

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")

```

**Validation**

The easiest way to validate a single field is to override the method `clean_<fieldname>()`

**View**

The view has to render the default form when it is first called and then either re-render it with error messages if the data is invalid, or process the data and redirect to a new page if the data is valid 

For forms that use a `POST request` to submit information to the server, the most common pattern is for the view to test against the POST request type `(if request.method == 'POST':)` to identify form validation requests and GET (using an else condition) to identify the initial form creation request. If you want to submit your data using a GET request, then a typical approach for identifying whether this is the first or subsequent view invocation is to read the form data (e.g. to read a hidden value in the form).

## Model Forms

 If you just need a form to map the fields of a single model then your model will already define most of the information that you need in your form: fields, labels, help text and so on. Rather than recreating the model definitions in your form, it is easier to use the `ModelForm` helper class to create the form from your model. This ModelForm can then be used within your views in exactly the same way as an ordinary Form.

**Example**

```python
from django.forms import ModelForm

from catalog.models import BookInstance

class RenewBookModelForm(ModelForm):
    class Meta:
        model = BookInstance
        fields = ['due_back']

```
## Generic editing views

Django abstracts much of this "boilerplate" for you, by creating generic editing views for creating, editing, and deleting views based on models. Not only do these handle the "view" behavior, but they automatically create the form class (a ModelForm) for you from the model.

## Things I want to know more about

Form Validation
