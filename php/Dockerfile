FROM php:8.1-fpm

WORKDIR /var/www/html

# Copy composer.lock and composer.json
COPY ./laravel/composer.lock ./laravel/composer.json /var/www/html/

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN composer install 

RUN cp .env.example .env

RUN php artisan key:generate

# Expose port 9000 and start php-fpm server
EXPOSE 9000

CMD ["php-fpm"]