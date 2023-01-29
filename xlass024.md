# DJANGO REST FRAMEWORK AND DOCKER

[Source](https://wsvincent.com/beginners-guide-to-docker/)

Docker is a platform designed to help developers build, share and run modern applications. It is a way to isolate and run entire applications.

Docker can be shared among team members so everyone is working on the same setup.

The downside is that docker is complex.

Under the hood docker is really just Linux Containers which are a type of virtualization.

Virtual machines take up so much size.

Docker is simply a way to implement Linux containers.

## Containers Vs  Virtual Environments

Virtual environments can only isolate Python packages only.

We can't run production databases or other services within venv co compared to Docker containers they are more limited.

## How to Install Docker

`docker --version` to check the Docker version you are running.

To confirm docker is installed correctly run `docker run hello-world`

To install `Docker Compose` run `sudo pip install docker-compose`.

A good command to inspect Docker is docker info.

## Images and Containers

An `image` is a snapshot in time of what a project contains.

A `container` is running instance of the image.

A baking analogy we can use here is as follows:

* A Dockerfile is the recipe for a cake
* An image is a snapshot of the recipe at a given time
* A docker-compose.yml says how to make the cake
* And the container is the actual, baked cake

## Creating an Image

First create a local directory on your computer for your code.

Define the image with a `Dockerfile`.

Add this single line of code to the `Dockerfile`

```
FROM python:3.7-alpine
```
After that run the command `docker image build` .

Image Layering exists for two main reasons:

* Each image layer is immutable-unchanged  like a git commit
* Performance - Docker caches the steps in the a `Dockerfile` to speed up the subsequent builds.

Fot this reason order matters in a Dockerfile.

## Containers

`docker-compose.yml` controls how to run the container.

Containers are `stateless` and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).

## Dockerized Django

 First we use `FROM to install python:3.7-alpine` as our base image and set two environment variables with `ENV`.
 
The first, `PYTHONDONTWRITEBYTECODE` will remove .pyc files from our container which is a good optimization. 

The second, `PYTHONUNBUFFERED` will buffer our output so it will look “normal” within Docker for us.

 `WORKDIR` command to create and set /code as our default directory within Docker. 
 
The `Pipfile` contains information on our software packages so we copy that over, too.

We then run `docker-composer.yml`

## Django for APIs

[source](https://djangoforapis.com/library-website-and-api/)

`Django REST Framework` works alongside the Django web framework to create web APIs.

Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON

The `__init__.py` indicates that the files in the folder are part of a Python package.

The rest framework also includes `serialization` and `parser/renderer` components that make it easy to build appropriate media types, hyperlinked relations for building well-connected systems, and great support for content negotiation

REST framework doesn't give you machine-readable hypermedia formats such as HAL, Collection+JSON API or HTML microformats

## Things I would like to know more about.

How Docker Caches the steps in a Dockerfile.