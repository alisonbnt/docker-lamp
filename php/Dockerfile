FROM php:7-apache
COPY php.ini /usr/local/etc/php/
RUN docker-php-source extract \
  && apt-get update \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev \
  && rm -rf /var/lib/apt/lists/* \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt \
  && a2enmod rewrite \
  && a2enmod ssl \
  && docker-php-source delete
