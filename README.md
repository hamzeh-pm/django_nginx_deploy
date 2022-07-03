# Django, Postgresql, Redis, Serve With NGINX

> a Django web project with postgresql database and redis cache server, serve with nginx through uwsgi

## technology use here

- Djagno - web framework
- Postgres - database
- Redis - cache
- Nginx - proxy server
- uwsgi - wsgi server

## ready to use

<<<<<<< HEAD
- create .env file in root of project

  - NGINX_PORT=8000 **example**
  - NGINX_CONF=production.nginx.conf

- create directory envs

  - create file db.env with variables

    - POSTGRES_NAME=
    - POSTGRES_USER
    - POSTGRES_PASSWORD

  - create file web.env with variables
    - DJANGO_SETTINGS_MODULE=core.settings.production
    - POSTGRES_NAME
    - POSTGRES_USER
    - POSTGRES_PASSWORD
    - POSTGRES_HOST
    - REDIS_PASSWORD
    - REDIS_HOST
    - REDIS_PORT

- create copy of web/core/settings/development.py next to itself
- rename it to production.py
- change DEBUG=False,
  SECRET_KEY=[openssl rand -base64 64],
  ALLOWED_HOSTS = ['production server host name']

- copy nginx/development.nginx.conf inside nginx folder
- rename it to production.nginx.conf
- change listen and server_name to your production server port and host name
=======
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
>>>>>>> ae62a7c6f94e298a6c87e1735c1972bb1928fca6
