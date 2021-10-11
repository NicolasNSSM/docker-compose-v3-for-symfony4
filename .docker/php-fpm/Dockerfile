FROM composer:2.1 as composer

FROM php:fpm

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apt-get update \
  && apt-get install --yes --no-install-recommends libpq-dev libzip-dev wget git zlib1g-dev \
  && docker-php-ext-install pdo_mysql zip opcache
