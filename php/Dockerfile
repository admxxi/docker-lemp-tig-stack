FROM php:7.1-fpm-alpine
#FROM php:5.6.33-fpm-alpine3.4
#FROM php:5.6.33-fpm-jessie

RUN apk update \
    && apk add libmcrypt-dev \
    && docker-php-ext-install mcrypt mysqli \
    && mkdir /app \
    && chown -R www-data:www-data /app \
    && rm /var/cache/apk/*

COPY www.conf /usr/local/etc/php-fpm.d/www.conf
COPY tune.ini /usr/local/etc/php/conf.d/tune.ini
#RUN usermod --non-unique --uid 1000 www-data \
#  && groupmod --non-unique --gid 1000 www-data \
# && chown -R www-data:www-data /var/www
#RUN usermod -u 1000 -o www-data
#RUN chown -R www-data:www-data /app
RUN ln -sf /dev/stdout /var/log/fpm-php.www.log
