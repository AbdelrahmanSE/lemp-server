FROM php:7.3.1-fpm-alpine

# COPY composer.lock composer.json /var/www/

WORKDIR /var/www

# RUN apk add composer
# Install dependencies
#RUN apt update && apt install -y \
#    build-essential \
#    mysql-client \
#    libpng-dev \
#    libjpeg62-turbo-dev \
#    libfreetype6-dev \
#    locales \
#    zip \
#    jpegoptim optipng pngquant gifsicle \
#    vim \
#    unzip \
#    git \
#    curl
#
## Clear cache
#RUN apt-get clean && rm -rf /var/lib/apt/lists/*
#
## Install extensions
#RUN docker-php-ext-install pdo_mysql mbstring zip exif pcntl
RUN docker-php-ext-install pdo_mysql mbstring bcmath
#RUN docker-php-ext-configure gd --with-gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/
#RUN docker-php-ext-install gd

# Install composer
#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Run composer
#RUN composer install
#
## Add user for laravel application
#RUN groupadd -g 1000 www
#RUN useradd -u 1000 -ms /bin/bash -g www www
#
## Copy existing application directory contents
#COPY . /var/www
#USER www
#COPY . /var/www
#RUN chown -R www:www /var/www
RUN apk add php7-mysqli php7-opcache php7-gd php7-mysqli php7-zlib php7-curl php7-phar php7-json php7-mbstring 

# Copy existing application directory permissions
RUN addgroup -S www && adduser -S www -G www
COPY --chown=www-data:www-data . /var/www
#RUN composer install --no-dev && php artisan config:cache && php artisan migrate:fresh --seed
# RUN composer install

#RUN php artisan migrate:fresh --seed --force
# Change current user to www

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]
