# Django. Database

## Database setup

** mysite/settings.py: module-level variables representing Django.**

* `ENGINE`: 'django.db.backends.mysql'
* `NAME`: the name of the database.
* `INSTALLED_APPS`: holds the name of the Django applications. Package and distribute for use by other projects. (eg. django.contrib.admin, django.contrib.auth ...)


migrate database (migrate: how django stores changes to your models)

```
> python manage.py migrate
```
- migrate looks at the INSTALLED_APPS setting
- creates any necessary database tables according to the database settings in setings.py
- database migration shipped with the app.

## Create models

models.py: single, definitive source of information about data.

django.db.models.Model 의 subclass로 각각의 모델이 존재한다. 각각의 모델은 class variables (db 필드를 나타냄)을 가지고 있다.

#### Fields
* CharField (required argument: max_length)
* DataTimeField
eg) Question.pub_date


## Activate models

model code make it possible to `create a database schema for this app` and `create a python database-access API or accessing entity objects`.

#### include the app in project = add a references to its configuration class in the INSTALLED_APPS

* makemigrations : let django know there are changes in models and changes to be stored as a migration.

```
> python manage.py makemigration polls (name of app's directory)
```

* sqlmigrate : Print the SQL for the named migration. (해당 앱에 대한 sql script를 프린트 한다.)

```
> python manage.py sqlmigrate polls 0001
```

* migrate : takes all the migrations that haven't been applied and runs them against your database. (sychronize the changes you made to your models)


1. change models (in models.py)
2. Run `python manage.py makemigrations` to create migrations for those changes
3. Run `python manage.py migrate` to apply those changes to the database

## Playing with the API

interactive python Shell
```
> python manage.py shell
```

이를 통해 model에 직접 접근할 수 있다.
