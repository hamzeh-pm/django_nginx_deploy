# Dockerize Django Project with Nginx and UWSGI

> Ready to deploy django docker container with help of nginx and uwsgi

## containers

- Django with pipenv
- Nginx
- postgres DB
- Redis Cache

**note** i push everything but it is better for you to add django.env and postgres.env
and djagno.core.settings.production.py to gitignore and provide user with template for security reasons

**note** create 2 folder db, cache in root of the project

**note** add your assets to assets folder and rest will be taking care of

**note** django.pytest.ini is for pytest-django module if your are using django unittest you can remove this file

### for production server
- change django.env file 
  DJANGO_SETTINGS_MODULE=core.settings.production
  
- in django.core.settings.production
  ALLOWED_HOSTS = list of your host name
  
- in docker-compose.yml
  change nginx section
    ports:
      - "8000:8000"
    *change the ports expose_port=docker_port(most be equal to listen port of nginx below)*
    
- in nginx.django.nginx.conf
  change server {
    listen      8000;
    server_name 127.0.0.1;
    charset     utf-8;
    
    *listen = your prefer post most be equal to right hand side port of right in abouve change
    server_name = name of your host or ip address of server*
