ARG ALPINE_VERSION=3.15
ARG PHP_VERSION=8.1.1

FROM php:${PHP_VERSION}-fpm-alpine${ALPINE_VERSION} as base

RUN docker-php-ext-install pdo_mysql

WORKDIR /var/www/html

COPY . .

RUN --mount=from=composer:2.3.5,source=/usr/bin/composer,target=/usr/bin/composer \
      composer install \
          --no-dev --no-ansi --no-plugins --no-progress --no-scripts \
          --classmap-authoritative --no-interaction \
          --quiet