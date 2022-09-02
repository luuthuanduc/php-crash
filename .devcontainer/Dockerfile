FROM alpine:3.16

RUN apk update && apk upgrade
RUN apk add bash
RUN apk add nginx
RUN apk add php81-fpm

COPY nginx /etc/nginx
COPY php /etc/php81
RUN mkdir /var/run/php
EXPOSE 80

CMD ["/bin/bash", "-c", "php-fpm81 && chmod 777 /var/run/php/php8-fpm.sock && chmod 755 /var/www/html/* && nginx -g 'daemon off;'"]