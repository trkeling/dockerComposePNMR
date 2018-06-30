FROM php:fpm
RUN docker-php-ext-install -j$(nproc) pdo_mysql\
    && docker-php-ext-install -j$(nproc) mysqli

RUN pecl install igbinary \
	&& pecl install redis-4.0.1 \
    && docker-php-ext-enable igbinary redis 
