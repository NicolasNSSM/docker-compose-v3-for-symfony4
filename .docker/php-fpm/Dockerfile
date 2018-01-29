FROM php:fpm

RUN apt-get update \
  && apt-get install --yes --no-install-recommends libpq-dev wget git zlib1g-dev \
  && docker-php-ext-install pdo_mysql zip opcache

COPY .docker/php-fpm/install-composer.sh /

RUN apt-get purge -y g++ \
    && apt-get autoremove -y \
    && rm -r /var/lib/apt/lists/* \
    && rm -rf /tmp/* \
    && sh /install-composer.sh \
    && rm /install-composer.sh

