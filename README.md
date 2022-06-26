# Dockerize Django Project with Nginx and UWSGI

> Ready to deploy django docker container with help of nginx and uwsgi

## containers

- Django with pipenv
- Nginx
- postgres DB
- Redis Cache

**note** i push everything but it is better for you to add django.env and postgres.env
and djagno.core.settings.production.py to gitignore and provide user with template for security reasons

**note** add your assets to assets folder and rest will be taking care of

**note** django.pytest.ini is for pytest-django module if your are using django unittest you can remove this file
