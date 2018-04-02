FROM php:fpm

RUN apt-get update \
  && apt-get install -y --no-install-recommends apt-utils libpq-dev wget git zip mcrypt curl libpng-dev libxml2-dev libicu-dev gnupg vim \
  && docker-php-ext-install pdo_pgsql pdo_mysql zip gd xml intl mbstring

RUN wget https://phar.phpunit.de/phpunit.phar && chmod +x phpunit.phar && mv phpunit.phar /usr/local/bin/phpunit

#composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && chmod +x composer.phar \
    && mv composer.phar /usr/local/bin/composer

#symfony
RUN mkdir -p /usr/local/bin \
    && curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony \
    && chmod a+x /usr/local/bin/symfony


RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get update && apt-get install -y nodejs build-essential
RUN npm install gulp-cli -g
RUN npm install gulp -D
