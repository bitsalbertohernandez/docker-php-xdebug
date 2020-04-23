FROM php:7.4-fpm
WORKDIR "/app" 
RUN apt-get update && apt-get install -y \
        zip \
        unzip \
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

# Install MySQL PDO
RUN docker-php-ext-install pdo_mysql

# Install Vim
RUN apt-get install vim -y

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Drush
RUN composer global require drush/drush

# Install git
RUN apt-get install git -y

# Install Codesniffer
RUN composer global require drupal/coder

# Install Drupal rules Codesniffer
RUN composer global require dealerdirect/phpcodesniffer-composer-installer

# Drush global
ENV PATH "$PATH:/root/.composer/vendor/bin"