FROM php:8.1.0-fpm

ARG UID=1000

USER root

RUN apt-get update && apt-get install -y \
    gnupg \
    g++ \
    procps \
    openssl \
    git \
    unzip \
    zlib1g-dev \
    libzip-dev \
    libfreetype6-dev \
    libpng-dev \
    libjpeg-dev \
    libicu-dev  \
    libonig-dev \
    libxslt1-dev \
    acl

RUN docker-php-ext-install \
    pdo pdo_mysql zip xsl gd intl opcache exif mbstring

RUN useradd -rm -d /home/user -s /bin/bash -g root -G sudo -u ${UID} user

USER user

COPY ./config/php.ini $PHP_INI_DIR/php.ini
