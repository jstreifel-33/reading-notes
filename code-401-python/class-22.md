# Django Forms and CRUD

Source: [MDN Tutorial - Working with Forms](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)

Django can utilize HTML forms to create, update and delete model instances.

Because Django is so cool, it also includes a Django Forms framework for taking care of most of the heavy lifting when working with forms.

## HTML Forms

Consider an HTML form:

```HTML
<!-- From MDN: -->
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```

In the above example, `action` determines where a form sends its data upon submission, while `method` determines what kind of request the data will be contained in.

The data gets sent to the server, and a bunch of stuff has to happen, such as validation, sanitation, feed-back to user, etc. It can be a lot of work. Django makes it less work.

## Django Form Handling

Django's form handling is pretty similar to how we normally render pages. A request is received to a view, the view executes necessary functions, and a template is rendered to the page.

Most specifically:

1. The form is displayed the first time it is requested.
2. Data is received from a form submission
3. Data is cleaned and validated
4. If any data is invalid, the form is re-displayed with user populated values and error messages.
5. If all data is valid, actions are performed accordingly
6. Once all actions are complete, the user is redirected.

## Django Forms

Forms can be made in Django using either functional views or Form classes.

### MDN Functional View example

```python
import datetime

from django.contrib.auth.decorators import login_required, permission_required
from django.shortcuts import get_object_or_404
from django.http import HttpResponseRedirect
from django.urls import reverse

from catalog.forms import RenewBookForm

@login_required
@permission_required('catalog.can_mark_returned', raise_exception=True)
def renew_book_librarian(request, pk):
    """View function for renewing a specific BookInstance by librarian."""
    book_instance = get_object_or_404(BookInstance, pk=pk)

    # If this is a POST request then process the Form data
    if request.method == 'POST':

        # Create a form instance and populate it with data from the request (binding):
        form = RenewBookForm(request.POST)

        # Check if the form is valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required (here we just write it to the model due_back field)
            book_instance.due_back = form.cleaned_data['renewal_date']
            book_instance.save()

            # redirect to a new URL:
            return HttpResponseRedirect(reverse('all-borrowed') )

    # If this is a GET (or any other method) create the default form.
    else:
        proposed_renewal_date = datetime.date.today() + datetime.timedelta(weeks=3)
        form = RenewBookForm(initial={'renewal_date': proposed_renewal_date})

    context = {
        'form': form,
        'book_instance': book_instance,
    }

    return render(request, 'catalog/book_renew_librarian.html', context)

```

### MDN Class example

```python
from django.forms import ModelForm

from catalog.models import BookInstance

class RenewBookModelForm(ModelForm):
    def clean_due_back(self):
       data = self.cleaned_data['due_back']

       # Check if a date is not in the past.
       if data < datetime.date.today():
           raise ValidationError(_('Invalid date - renewal in past'))

       # Check if a date is in the allowed range (+4 weeks from today).
       if data > datetime.date.today() + datetime.timedelta(weeks=4):
           raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))

       # Remember to always return the cleaned data.
       return data

    class Meta:
        model = BookInstance
        fields = ['due_back']
        labels = {'due_back': _('Renewal date')}
        help_texts = {'due_back': _('Enter a date between now and 4 weeks (default 3).')}

```

## Additional Resources

MDN: [Creating a Home Page](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Home_page) and [Generic List and Detail Views](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Generic_views)
