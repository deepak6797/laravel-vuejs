FROM php:7.4-fpm

WORKDIR /var/www/html

RUN apt-get update && apt-get install -y curl libpng-dev libonig-dev libxml2-dev libzip-dev zip npm && \
    docker-php-ext-configure zip && \
    docker-php-ext-install zip pdo pdo_mysql mbstring exif pcntl bcmath gd && \
    apt clean && rm -rf /var/lib/apt/lists/*