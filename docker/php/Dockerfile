FROM php:5.5-fpm

RUN apt-get update && apt-get install -y \
    libicu-dev \
    nodejs \
    npm \
    rubygems \
    && docker-php-ext-install mysql pdo_mysql mbstring intl opcache \
    && pecl install apcu-4.0.10 xdebug \
    && echo "extension=apcu.so" > /usr/local/etc/php/conf.d/apcu.ini

RUN npm install -g uglify-js uglifycss
RUN gem install sass

ADD xdebug.ini /usr/local/etc/php/conf.d/
ADD symfony.ini /usr/local/etc/php/conf.d/

RUN echo "\n\nenv[SYMFONY__DATABASE__HOST] = \${DB_PORT_3306_TCP_ADDR}" >> /usr/local/etc/php-fpm.conf \
    && echo "env[SYMFONY__DATABASE__CHARSET] = 'utf8'" >> /usr/local/etc/php-fpm.conf \
    && echo "env[SYMFONY__DATABASE__DATABASE] = \${DB_ENV_MYSQL_DATABASE}" >> /usr/local/etc/php-fpm.conf \
    && echo "env[SYMFONY__DATABASE__USER] = 'root'" >> /usr/local/etc/php-fpm.conf \
    && echo "env[SYMFONY__DATABASE__PASSWORD] = \${DB_ENV_MYSQL_ROOT_PASSWORD}" >> /usr/local/etc/php-fpm.conf

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony