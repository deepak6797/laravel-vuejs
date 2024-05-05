FROM php:7.4-fpm

WORKDIR /var/www/html

# COPY ./laravelapp .
# COPY ./laravelapp/database ./database

RUN apt-get update && apt-get install -y curl libpng-dev libonig-dev libxml2-dev libzip-dev zip npm && \
    docker-php-ext-configure zip && \
    docker-php-ext-install zip pdo pdo_mysql mbstring exif pcntl bcmath gd && \
    apt clean && rm -rf /var/lib/apt/lists/*

# RUN a2enmod rewrite

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# RUN npm install && composer install

# CMD php artisan serve --host=0.0.0.0 --port=9000
# ENTRYPOINT [ "tail", "-f", "/dev/null" ]
