FROM php:7.2-apache

# Install required librairies
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

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Configure PHP extensions
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

# Install PHP extensions
RUN docker-php-ext-install mysqli zip gd intl

# Enable Apache modules
RUN a2enmod rewrite && a2enmod headers && a2enmod mime

# Copy custom files
COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./vhost.conf /etc/apache2/sites-enabled/000-default.conf

WORKDIR /var/www

CMD apachectl -D FOREGROUND