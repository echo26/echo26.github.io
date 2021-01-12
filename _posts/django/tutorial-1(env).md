# Django. Set environment

## Create a project (environment set up)
create `mysite` directory. 
```
django-admin startproject mysite
```

file structure
```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```

**mysite/: root direcotry. rename free**

**manage.py: A command-line utility that lets you interact with this Django project in various ways.**

**inner mysite/: the actual Python package for your project. Name = package name to be used to import anything inside it**

**__init__.py : empty file tells Python that this directory should be considered a Python package.**

**settings.py : configuration for this Django project.**

**urls.py: The URL declarations for this Django project. In other words, "table of contents of django-powered site.**

**asgi.py: an entry-point for asgi-compatible web server**

**wsgi.py: an entry-point for wsgi-compatible web server**


## Develop server
* Run django server
```
> python manage.py runserver
```

## create the polls app

* App: web application that do somethings. An app can be in multiple projects. Apps can live anywhere on your Python path.
* Projects : collection of configuration and apps for particular website. Able to contain multiple apps. 


Create polls app in the same directory of manage.py file. imported as its own top-level module.
```
> python manage.py startapp polls
```

file structure
```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```

* view.py : takes a web request and returns a web response.

* urls.py : created to URLconf in poll directory.

