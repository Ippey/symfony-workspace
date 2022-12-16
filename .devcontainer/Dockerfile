FROM php:8.1-fpm

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | sudo -E bash && \
    apt install symfony-cli \
                sqlite-devel
