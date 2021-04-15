# Django Polls Tutorial Sample Application - Version 3.0

* This repository includes all the steps through the end of https://docs.djangoproject.com/en/3.1/intro/tutorial04/#write-a-minimal-form

* But now the database has now been configured to connect to an external postgresql database with the password and host passed in as environment variables:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'mydatabase',
        'USER': 'mydatabaseuser',
        'PASSWORD': get_env_value('DATABASE_PASSWORD'),
        'HOST': get_env_value('ENDPOINT'),
        'PORT': '5432',
    }
}
```
  - I guess that probably means the poll question and two choices that were included in the sqlite database are not going to be there.


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
