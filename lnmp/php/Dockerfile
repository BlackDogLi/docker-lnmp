# Use an official PHP runtime as a parent image
FROM php:7.1-fpm
MAINTAINER liyu <lzly216@163.com>

# Set the timezone
ENV TimeZone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TimeZone /etc/localtime && echo $TimeZone > /etc/timezone

# Install package and PHP Core extensions
RUN apt-get update && apt-get install -y \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/incldue/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-exit-install zip \
    && docker-php-exit-install pdo_mysql \
    && docker-php-exit-install opcache \
    && docker-php-exit-install mysqli \
    && rm -r /var/lib/apt/lists/*

# Copy extensions had downloadedl
COPY ./pkg/redis.tgz /home/redis.tgz

# Install PECL extensions (Redis)
RUN pecl install /home/redis.tgz && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini

# Install Composer
ENV COMPOSER_HOME /root/composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV PATH $COMPOSER_HOMT/vendor/bin:$PATH

RUN rm -f /home/redis.tgz \

# Set the working directory to /data/web
WORKDIR /data/web

# Write Permisson
#RUN usermod -u 1000 www-data