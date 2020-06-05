ARG PHP_VERSION
FROM php:$PHP_VERSION-fpm-alpine

RUN apk update; \
    apk upgrade; \
    apk add libxml2-dev \
    libpng-dev \
    icu-dev \
    libxslt-dev \
    libzip-dev \
    composer; \
    docker-php-ext-configure gd --with-gd --with-webp-dir --with-jpeg-dir \
    --with-png-dir --with-zlib-dir --with-xpm-dir --with-freetype-dir \
    --enable-gd-native-ttf; \
    docker-php-ext-install bcmath gd intl pdo_mysql soap xsl zip;

CMD ["php-fpm"]

EXPOSE 9000
