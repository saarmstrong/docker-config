FROM  php:5.6-fpm
RUN apt-get update && apt-get install -y  --no-install-recommends apt-utils \
    g++ \
    curl \
    openssl \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng12-dev \
    libicu-dev \
    libmcrypt-dev \
    vim 
RUN apt-get install -y libxml2-dev

RUN docker-php-ext-configure mcrypt --with-mcrypt \
	&& docker-php-ext-install mcrypt 

RUN docker-php-ext-install pdo_mysql 
RUN docker-php-ext-configure intl  
RUN docker-php-ext-install intl
RUN docker-php-ext-install soap  mbstring 
RUN pecl install redis && docker-php-ext-enable redis 
