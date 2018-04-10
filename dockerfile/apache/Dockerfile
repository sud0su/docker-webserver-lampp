FROM php:7.1-apache

RUN apt-get -y update --fix-missing
RUN apt-get upgrade -y

# libraries
RUN apt-get -y install --fix-missing apt-utils build-essential git curl libssl-dev libcurl4-openssl-dev pkg-config
# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# PHP Extensions
RUN apt-get -y install libmcrypt-dev libsqlite3-dev libsqlite3-0 mysql-client zlib1g-dev libicu-dev zip libfreetype6-dev libjpeg62-turbo-dev libpng12-dev
RUN docker-php-ext-install mcrypt \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install pdo_sqlite \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install curl \
    && docker-php-ext-install tokenizer \
    && docker-php-ext-install json \
    && docker-php-ext-install zip \
    && docker-php-ext-install -j$(nproc) intl \
    && docker-php-ext-install mbstring \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# xdebug
RUN pecl install xdebug-2.5.0
RUN docker-php-ext-enable xdebug

# Enable apache modules
RUN a2enmod rewrite headers