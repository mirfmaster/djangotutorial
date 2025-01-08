# Django tutorial

## Python
- By using __init__.py indicating that the folder is a python package, and it can use dot notation. (e.g: "polls.apps.PollsConfig")
- Python uses indentation to identify block code
- Python uses virtual env to managing package

## Projects and Apps
> Django apps are “pluggable”: You can use an app in multiple projects, and you can distribute apps, because they don’t have to be tied to a given Django installation.

### Important files
#### Projects
- manage.py
    - It's kind of `artisan` from laravel, one stop script to operate with django
- {project}/settings.py
    - any apps created should be registered on array INSTALLED_APPS
- {project}/urls.py
    - any apps route should be included in the main project url

## Notes 
Django is using MVC pattern
- Model -> models.py
- View -> templates/{modules}/**
- Controller -> views.py

Django has helper function stored on django.shortcuts package

- to self package import use 
`from .models import Question`

- Playing with django shell
`python manage.py shell`


### Model
- Doing migration
`python manage.py migrate`

- Sync migration file with model, this will make a migration file
`python manage.py makemigrations polls`

- Migrating the migration file
`python manage.py sqlmigrate polls 0001`

### HTML Templating
Django use jinja for the render and templating, it has the same feature with `blade` templating

- Templating system
```py
# Controller
from django.shortcuts import render, get_object_or_404

return render(request, "polls/index.html", context)

# HTML Usage
## Looping
{% for item in items%}

## Variable rendering from the context passed
{{ variable }}

## If templating
{% if conditions %}
{% else %}
{% endif %}

forloop.counter indicates how many times the for tag has gone through its loop
```

# TODO:
- Need to read django.shortcuts package
https://docs.djangoproject.com/en/5.1/topics/http/shortcuts/#module-django.shortcuts
- Need to know how to altering tables in django model and migration
