FROM ubuntu:xenial

COPY docker-php-entrypoint /usr/bin/docker-php-entrypoint

RUN apt-get update -y \
&& apt-get install -y \
  php7.0 \
  php7.0-fpm \
  php7.0-cli \
  php7.0-common \
  php7.0-curl \
  php7.0-gd \
  php7.0-json \
  php7.0-mcrypt \
  php7.0-mysql \
  php7.0-opcache \
  php7.0-readline \
  php7.0-soap \
  php7.0-xml \
  curl \
  zip \
&& rm -rf /var/lib/apt/lists/*

COPY php-fpm.d/php-fpm.conf /etc/php/7.0/fpm/php-fpm.conf
COPY php-fpm.d/docker.conf /etc/php/7.0/fpm/docker.conf
COPY php-fpm.d/zz-docker.conf /etc/php/7.0/fpm/zz-docker.conf

ENTRYPOINT ["docker-php-entrypoint"]
WORKDIR /var/www/html
EXPOSE 9000

CMD ["php-fpm7.0"]
