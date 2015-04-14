FROM php:5.6-fpm
MAINTAINER louisbl <louis@beltramo.me>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
  libpng12-dev \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libmcrypt-dev \
  libcurl4-openssl-dev \
  libpq-dev \
  libssl-dev \
  libzip-dev \
  && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install \
    gd \
    mbstring \
    mcrypt \
    mysqli \
    opcache \
    pdo_mysql \
    pdo_pgsql \
    pgsql \
    zip

COPY php-fpm.conf /usr/local/etc/php-fpm.conf
