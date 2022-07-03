# Django, Postgresql, Redis, Serve With NGINX

> a Django web project with postgresql database and redis cache server, serve with nginx through uwsgi

## technology use here

- Djagno - web framework
- Postgres - database
- Redis - cache
- Nginx - proxy server
- uwsgi - wsgi server

## ready to use

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
