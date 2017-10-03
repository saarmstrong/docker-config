FROM  php:5.6-fpm
RUN apt-get update && apt-get install -y \
    curl \
    openssl \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng12-dev \
    mcrypt \
    vim 
RUN  apt-get install -y libmcrypt-dev
RUN  docker-php-ext-install pdo_mysql 
RUN  docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN  docker-php-ext-install gd 
RUN  docker-php-ext-install mcrypt 
RUN  docker-php-ext-install curl 
RUN  docker-php-ext-install soap 
RUN  docker-php-ext-install intl 
RUN  docker-php-ext-install memcache 
RUN  docker-php-ext-install imagick 