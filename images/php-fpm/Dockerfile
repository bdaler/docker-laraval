FROM php:7.1-fpm

MAINTAINER Daler Bahritdinov <dalerkbtut@gmail.com>

RUN apt-get update && apt-get install -y \
	git libmcrypt-dev mysql-client unzip \
    && docker-php-ext-install mcrypt pdo_mysql \
    && rm -r /var/lib/apt/lists/*

# Set timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/Europe/Moscow /etc/localtime
RUN "date"

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

WORKDIR /var/www/laravel