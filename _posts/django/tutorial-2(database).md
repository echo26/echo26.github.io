# Django. Database

## Database setup

** mysite/settings.py: module-level variables representing Django.**

* `ENGINE`: 'django.db.backends.mysql'
* `NAME`: the name of the database.
* `INSTALLED_APPS`: holds the name of the Django applications. Package and distribute for use by other projects. (eg. django.contrib.admin, django.contrib.auth ...)


migrate database
```
> python manage.py migrate
```
- migrate looks at the INSTALLED_APPS setting
- creates any necessary database tables according to the database settings in setings.py
- database migration shipped with the app.

## Create models

models.py: single, definitive source of information about data.
