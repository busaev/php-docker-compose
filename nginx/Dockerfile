FROM nginx

ADD ./nginx/default.conf /etc/nginx/conf.d/


RUN echo "daemon off;" >> /etc/nginx/nginx.conf

WORKDIR /var/www/site


CMD service nginx start
