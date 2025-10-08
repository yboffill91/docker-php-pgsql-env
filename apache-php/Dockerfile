
FROM php:8.3-apache

RUN apt-get update && apt-get install -y \
    libpq-dev \
    git \
    zip \
    unzip \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo pdo_pgsql pgsql

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Por defecto, la carpeta de trabajo de Apache es /var/www/html.
# La montaremos en el docker-compose.yml.