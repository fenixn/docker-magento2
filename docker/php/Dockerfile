ARG PHP_VERSION
FROM php:$PHP_VERSION-fpm-alpine

RUN apk update; \
    apk upgrade; \
    apk add libxml2-dev \
    libpng-dev \
    icu-dev \
    libxslt-dev; \
    docker-php-ext-install bcmath gd intl pdo_mysql soap xsl zip;
