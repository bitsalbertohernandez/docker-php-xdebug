FROM php:7.4-fpm
WORKDIR "/app" 
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install bcmath

RUN apt-get update \
  && apt-get install -y zlib1g-dev libicu-dev g++ \
  && docker-php-ext-configure intl \
  && docker-php-ext-install intl

# Install xdebug
RUN pecl install xdebug-2.9.4 \
    && docker-php-ext-enable xdebug 

RUN docker-php-ext-install pdo_mysql

RUN apt-get install vim -y