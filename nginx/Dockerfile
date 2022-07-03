FROM nginx:latest

ARG CONF_FILE
COPY nginx.conf /etc/nginx/nginx.conf
COPY $CONF_FILE /etc/nginx/sites-available/$CONF_FILE
RUN mkdir /etc/nginx/sites-enabled
RUN ln -s /etc/nginx/sites-available/$CONF_FILE /etc/nginx/sites-enabled/
CMD ["nginx", "-g", "daemon off;"]