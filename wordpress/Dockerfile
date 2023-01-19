ARG PHP_VERSION=7.4

FROM php:${PHP_VERSION}-apache

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    nano \
    zlib1g-dev \
    libzip-dev \
    libjpeg-dev\
    libpng-dev\
    libfreetype6-dev \
    libpq-dev \
    libicu-dev g++ \
    gnupg \
    apt-transport-https

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV COMPOSER_MEMORY_LIMIT=-1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

RUN docker-php-ext-configure gd --with-freetype --with-jpeg

RUN docker-php-ext-install mysqli zip gd intl

RUN a2enmod rewrite && a2enmod headers && a2enmod mime

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./vhost.conf /etc/apache2/sites-enabled/000-default.conf

WORKDIR /var/www

CMD apachectl -D FOREGROUND