# Django Polls Tutorial Sample Application - Version 3.0

* This repository includes all the steps through the end of https://docs.djangoproject.com/en/3.1/intro/tutorial04/#write-a-minimal-form

* But now the database has now been configured to connect to an external postgresql database with the password and host passed in as environment variables. To do this, the following lines have been added to `settings.py`:
```
import os

from django.core.exceptions import ImproperlyConfigured
def get_env_value(env_variable):
    try:
        return os.environ[env_variable]
    except KeyError:
        error_msg = 'Set the {} environment variable'.format(env_variable)
        raise ImproperlyConfigured(error_msg)

...

# And the databases section amended with:
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': get_env_value('DATABASE_NAME'),
        'USER': get_env_value('DATABASE_USER'),
        'PASSWORD': get_env_value('DATABASE_PASSWORD'),
        'HOST': get_env_value('DATABASE_HOST'),
        'PORT': '5432',
    }
}
```


## Usage
```
pip install -r requirements.txt # install required python modules
cd mysite
python manage.py runserver 0.0.0.0:8000 # to listen on port 8000
```

- Navigate to http://localhost:8000/polls
- The admin dashboard is accessible at http://localhost:8090/admin/
- The admin user's credentials:
  - username: a
  - password: a
