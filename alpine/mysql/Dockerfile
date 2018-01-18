FROM php:7-alpine

MAINTAINER Muhammad Zackky <m.zackky@gmail.com>

RUN apk --no-cache add libmcrypt-dev libxml2-dev openssl openldap openldap-dev

RUN docker-php-ext-install mbstring; \
    docker-php-ext-install mcrypt; \
    docker-php-ext-install pdo; \
    docker-php-ext-install pdo_mysql; \
    docker-php-ext-install tokenizer; \
    docker-php-ext-install xml; \
    docker-php-ext-install zip; \
    docker-php-ext-install ldap

WORKDIR /app

EXPOSE 8000

ENTRYPOINT ["php", "artisan"]
CMD ["list"]
