FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    zlib1g-dev \
    libjpeg-dev\
    libpng-dev\
    libfreetype6-dev \
    libpq-dev \
    libicu-dev g++ \
    gnupg \
    apt-transport-https

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

RUN docker-php-ext-install mysqli zip gd intl

RUN a2enmod rewrite && a2enmod headers && a2enmod mime

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./vhost.conf /etc/apache2/sites-enabled/000-default.conf

WORKDIR /var/www

CMD apachectl -D FOREGROUND