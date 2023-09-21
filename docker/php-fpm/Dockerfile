FROM php:8.2-fpm-alpine

RUN apk --no-cache add \
        $PHPIZE_DEPS \
        nano \
        git \
        apache-ant \
        openssl \
        supervisor \
        libxslt-dev \
        icu-dev \
        libjpeg-turbo \
        libpng-dev \
        libpng \
        libjpeg-turbo-dev \
        freetype-dev \
        freetype \
    && docker-php-ext-configure gd \
        --with-gd \
        --with-freetype-dir=/usr/include/ \
        --with-png-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/ \
    && pecl install \
        apcu \
        mongodb \
        redis \
    && docker-php-ext-install \
        bcmath \
        opcache \
        pdo \
        pdo_mysql \
        xsl \
        intl \
        gd \
        zip \
    && docker-php-ext-enable \
        apcu \
        mongodb \
        redis \
    && apk del --no-cache \
        freetype-dev \
        libpng-dev \
        libjpeg-turbo-dev

# Install packages
RUN apk add --no-cache curl git build-base zlib-dev oniguruma-dev autoconf bash

# Postgres
RUN apk add --no-cache libpq-dev && docker-php-ext-install pdo_pgsql

# Configure non-root user.
RUN apk --no-cache add shadow

# Source code
COPY ./ /var/www
WORKDIR /var/www

# Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

CMD php-fpm

EXPOSE 8080