FROM php:7.3.12-fpm-buster
COPY ./sources.list /etc/apt/sources.list 
RUN apt-get update && apt-get install -y \
    apt-utils \
    zlib1g-dev \
    && docker-php-ext-install mysqli pdo pdo_mysql\
    && pecl install redis-5.1.1 \
    && pecl install yaf-3.0.8 \
    && pecl install xdebug-2.7.2 \
    && pecl install protobuf-3.9.2 \
    && pecl install grpc-1.25.0 \
    && docker-php-ext-enable redis xdebug yaf protobuf grpc\
    && cd /usr/local/etc/php \
    && touch php.ini
