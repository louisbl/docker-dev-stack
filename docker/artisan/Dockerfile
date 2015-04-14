FROM php:5.6-cli
MAINTAINER louisbl <louis@beltramo.me>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    autoconf \
    build-essential \
    ca-certificates \
    curl \
    git \
    imagemagick \
    libbz2-dev \
    libcurl4-openssl-dev \
    libevent-dev \
    libffi-dev \
    libfreetype6-dev \
    libglib2.0-dev \
    libjpeg-dev \
    libjpeg62-turbo-dev \
    liblzma-dev \
    libmagickcore-dev \
    libmagickwand-dev \
    libmcrypt-dev \
    libmysqlclient-dev \
    libncurses-dev \
    libpng12-dev \
    libpq-dev \
    libreadline-dev \
    libsqlite3-dev \
    libssl-dev \
    libxml2-dev \
    libxslt-dev \
    libyaml-dev \
    libzip-dev \
    openssh-client \
    wget \
    zlib1g-dev \
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

RUN mkdir -p /var/www/html && chown -R www-data:www-data /var/www/html
WORKDIR /var/www/html

USER www-data

ENTRYPOINT ["php", "artisan"]
CMD ["--help"]
