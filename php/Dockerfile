FROM php:8.3.13-fpm

# Install required PHP extensions
RUN apt-get update && apt-get install -y \
    unzip zip git curl libpng-dev libjpeg-dev libfreetype6-dev libonig-dev libxml2-dev \
    libzip-dev libpq-dev libicu-dev libwebp-dev libxpm-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp \
    && docker-php-ext-install gd pdo pdo_mysql mbstring zip opcache intl xml \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install drush
RUN curl -OL https://github.com/drush-ops/drush-launcher/releases/latest/download/drush.phar \
    && chmod +x drush.phar \
    && mv drush.phar /usr/local/bin/drush

COPY ./php/php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html/web