FROM php:fpm

RUN apt-get update \
  && apt-get install -y --no-install-recommends apt-utils libpq-dev wget git zip mcrypt curl phpunit libpng-dev libxml2-dev libicu-dev \
  && docker-php-ext-install pdo_pgsql pdo_mysql zip gd xml intl mbstring


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
