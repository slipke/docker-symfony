FROM ubuntu:14.04

RUN apt-get update && apt-get install -y \
    ant \
    nodejs \
    ruby \
    npm \
    git \
    curl \
    php5 \
    php5-cli \
    php5-json \
    php5-intl \
    php5-mysql

RUN npm install -g uglify-js uglifycss
RUN gem install sass

RUN usermod -u 1000 www-data
RUN sed -i "s@;date.timezone =@date.timezone = Europe/Berlin@" /etc/php5/cli/php.ini

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

WORKDIR /var/www/symfony
VOLUME /var/www/symfony