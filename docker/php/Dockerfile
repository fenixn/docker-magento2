ARG PHP_VERSION
FROM php:$PHP_VERSION-fpm-alpine

RUN apk update; \
    apk upgrade; \
    apk add libxml2-dev \
    freetype \
    libpng \
    libjpeg-turbo \
    freetype-dev \
    libpng-dev \
    libjpeg-turbo-dev \
    icu-dev \
    libxslt-dev \
    libzip-dev \
    composer; \
    docker-php-ext-configure gd \ 
        --with-gd \
        --with-freetype-dir=/usr/include/ \
        --with-png-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/; \
    NPROC=$(grep -c ^processor /proc/cpuinfo 2>/dev/null || 1); \
    docker-php-ext-install -j${NPROC} gd; \
    docker-php-ext-install bcmath intl pdo_mysql soap xsl zip;

CMD ["php-fpm"]

EXPOSE 9000
