FROM  php:5.6-fpm
RUN apt-get update && apt-get install -y \
    g++ \
    curl \
    openssl \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng12-dev \
    libicu-dev \
    libmcrypt-dev \
    vim 
RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install pdo_mysql 
RUN docker-php-ext-configure mcrypt  
RUN docker-php-ext-configure intl  
RUN docker-php-ext-install -j$(nproc) mcrypt intl
RUN docker-php-ext-install intl 
#RUN docker-php-ext-install intl soap  mbstring 
RUN pecl install redis && docker-php-ext-enable redis
