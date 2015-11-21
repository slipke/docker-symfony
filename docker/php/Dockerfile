FROM php:5.5-fpm

RUN apt-get update && apt-get install -y \
    libicu-dev \
    nodejs \
    npm \
    rubygems \
    && docker-php-ext-install pdo_mysql mbstring intl

RUN npm install -g uglify-js uglifycss
RUN gem install sass

ADD symfony.ini /usr/local/etc/php/conf.d/
ADD symfony.pool.conf /etc/php5/fpm/pool.d/

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony