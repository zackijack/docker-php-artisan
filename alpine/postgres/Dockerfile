FROM php:7-alpine

MAINTAINER Muhammad Zackky <m.zackky@gmail.com>

RUN apk --no-cache add libmcrypt-dev libxml2-dev openssl postgresql-dev

RUN docker-php-ext-install \
        mbstring \
        mcrypt \
        pdo \
        pdo_pgsql \
        tokenizer \
        xml \
        zip  

WORKDIR /app

EXPOSE 8000

ENTRYPOINT ["php", "artisan"]
CMD ["list"]
