# Docker and Django REST Framework

## Docker

Source: [WSVincent - A Beginner's Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)

Docker is an alternative to virtual environments, which encapsulates an application completely. It is system agnostic, so you can ensure that everyone on a team is working with the same setup, regardless of OS.

The downside to all of this is that Docker is a complex tool. That said, let's get into it.

### Linux Containers

At it's core, Docker is just a tool used to implement virtual **Linux containers**. Most computers rely on Linux at some level, so Docker builds from that level up, ensuring that a container is built a specific way.

Linux containers differ from virtual environments in that virtual environments only isolate Python packages. A Linux container is an entire system isolation.

### Using Docker

`docker run hello-world` will run our first demo container. It downloads an official image and creates a container from it.

`docker info` can be used to inspect Docker.

`ls -la` will inspect containers. `-la` is required to include stopped containers.

### Images and Containers

The reading uses the following analogy to explain images and containers:

* A `Dockerfile` is the recipe for a cake
* An *image* is a snapshot of the recipe at a given time
* A `docker-compose.yml` says how to make the cake
* And the *container* is the actual, baked cake

[Docker Hub](https://hub.docker.com/) can be used to get official images.

**Dockerfile** must be built manually and must start with a `FROM` command. They are read from top to bottom.

```Python
#Reading example:

# Dockerfile
FROM python:3.7-alpine
```

After creating the `Dockerfile` an image can be built using `docker image build .`.

**`docker-compose.yml`** defines our container. Order of code here is also important (top-to-bottom).

```Python
#Reading example:

# docker-compose.yml
version: '3.7'

services:
  web:
    build: .
    command: python /code/manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - 8000:8000
```

Once you've defined your image and container, `docker-compose up --build` can be used to run build and run both in one command.

## Django REST Framework

Source: [Django for APIs](https://djangoforapis.com/library-website-and-api/)

Django REST Framework is a tool that works alongside Django to create web APIs. It is not standalone, and must be added on top of Django.

Start by creating a Django project and app as usual, performing migrations and updating settings as needed.

Create a model, superuser, and basic display using views and templates.

Once your basic Django site is up, it's time to get into the REST framework.

### Using Django REST Framework

Start by installing Django REST Framework

`$ pipenv install djangorestframework~=3.11.0`

and add `'rest_framework'` to your `INSTALLED_APPS` in settings.py.

Create a new api app, and also add that to `INSTALLED_APPS`.

API endpoints are added just like traditional routes, inside of urls.py.

### The View

Once the urls are set up, we'll need our view. Create an API view extending the proper generic view:

```Python
#Reading example:

# api/views.py
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```

### The Serializers

A serializer translates data into a web friendly format, usually JSON, to be sent from our endpoint.

Create a `serializers.py` file within the api app:

```Python
#From reading:

# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```

It's fairly straightforward, but we need to import from rest_framework, extend the ModelSerializer class and then define the Meta class that states our model and fields to be serialized.

That's all set.

### cURL

Now we can run our server, and open another terminal.

`curl` can be used to make a basic GET request to a url.

`$ curl http://127.0.0.1:8000/api/`

This should reach out and touch our API, getting our model data back as JSON! Unsurprisingly for Django, it really is that simple.

## Additional Resources

[Official Django REST Framework Tutorial](https://learndjango.com/tutorials/official-django-rest-framework-tutorial-beginners)
