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

# Set memory limit
RUN echo "memory_limit=1024M" > /usr/local/etc/php/conf.d/memory-limit.ini

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Display version information
RUN composer --version

RUN mkdir -p /var/www && chown -R www-data:www-data /var/www
WORKDIR /var/www/

USER www-data

ENTRYPOINT ["composer"]
CMD ["--help"]
