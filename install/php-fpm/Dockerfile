FROM php:7.4-fpm

MAINTAINER Quan Duong <quandv.125@gmail.com>

RUN apt-get update && \
    apt-get install -y \
    git \
    make \
    supervisor \
    curl gnupg \
    nano \
    libfreetype6-dev \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libgmp-dev \
    libonig-dev \
    libzip-dev \
    libldap2-dev \
    libxml2-dev \
    zip \
    unzip \
    netcat \
    sqlite3 \
    libsqlite3-dev && \
    docker-php-ext-install gd pdo pdo_mysql mbstring intl pdo_sqlite zip gmp bcmath pcntl ldap sysvmsg exif
        

COPY symfony.pool.conf /usr/local/etc/

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# install php composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# install node 12.x and npm
RUN curl -sL https://deb.nodesource.com/setup_12.x  | bash -
RUN apt-get -y install nodejs

# php.ini
COPY ./php.ini /usr/local/etc/php/php.ini

# Supervisord
COPY ./supervisord.conf /etc/supervisor/conf.d/supervisord.conf    

# install Application

WORKDIR /var/www/html/blog

#EXPOSE 9000
CMD ["php-fpm", "-F"]

