FROM php:8.3.13-fpm

# Install required PHP extensions
RUN apt-get update && apt-get install -y \
    git unzip libpng-dev libjpeg-dev libfreetype6-dev libonig-dev libzip-dev libxml2-dev \
    && docker-php-ext-install zip pdo pdo_mysql xml opcache \
    && pecl install xdebug && docker-php-ext-enable xdebug

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY ./php/php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html/web