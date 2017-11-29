FROM nginx

ADD ./nginx/default.conf /etc/nginx/conf.d/


RUN echo "daemon off;" >> /etc/nginx/nginx.conf


RUN apt-get update && apt-get install -y curl gnupg apt-utils vim

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get update && apt-get install -y nodejs build-essential
RUN npm install gulp-cli -g
RUN npm install gulp -D

WORKDIR /var/www/site


CMD service nginx start
