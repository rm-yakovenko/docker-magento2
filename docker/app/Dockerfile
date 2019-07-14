FROM php:7.2-fpm-stretch

RUN echo "deb http://deb.debian.org/debian stretch-backports main" >> /etc/apt/sources.list && \
    apt-get -y -qq update && \
    apt-get -y -qq install  git unzip libpng-dev libjpeg-dev libfreetype6-dev libicu-dev libzip-dev libxml2-dev libxslt-dev libsodium-dev --no-install-recommends && \
    apt-get -y -qq -t stretch-backports install libsodium-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install -j$(nproc) pdo_mysql bcmath gd intl opcache zip soap xsl && \
    pecl install apcu libsodium && \
    docker-php-ext-enable apcu && \
    apt-get clean && \
    rm -r /var/lib/apt/lists/* && \
    rm -rf /var/cache/apt/* && \
    rm -rf /tmp/* && \
    curl -Lo /usr/bin/composer https://getcomposer.org/composer.phar && \
    chmod +x /usr/bin/composer

ARG XDEBUG

RUN if [ $XDEBUG ]; then pecl install xdebug && docker-php-ext-enable xdebug; fi