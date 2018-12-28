FROM php:7.3-cli-alpine
RUN apk update && apk add --no-cache \
        freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev \
        icu-libs icu-dev \
        libxml2-dev \
        postgresql-libs postgresql-dev \
        libzip zlib-dev libzip-dev \
    && docker-php-ext-configure gd \
        --with-gd \
        --with-freetype-dir=/usr/include/ \
        --with-png-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/ \
    && NPROC=$(grep -c ^processor /proc/cpuinfo 2>/dev/null || 1) \
    && docker-php-ext-install -j${NPROC} gd intl soap bcmath pdo pdo_pgsql pgsql zip\
    && apk del freetype-dev libpng-dev libjpeg-turbo-dev libxml2-dev icu-dev \
        postgresql-dev zlib-dev libzip-dev
