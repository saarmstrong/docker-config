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
RUN docker-php-ext-install soap mbstring
RUN docker-php-ext-install mysqli
RUN pecl install redis && docker-php-ext-enable redis 

RUN pecl install xdebug && docker-php-ext-enable xdebug
RUN printf "xdebug.remote_port=9999\n xdebug.remote_enable=on\n xdebug.remote_connect_back=1 " >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN sed -i -e "s/;error_log = log\/php-fpm.log/error_log = \/var\/log\/php-fpm.log/g" /usr/local/etc/php-fpm.d/www.conf
RUN sed -i -e "s/;log_level = notice/log_level = debug/g" /usr/local/etc/php-fpm.d/www.conf
RUN sed -i -e "s/;php_admin_flag[log_errors] = on/;php_admin_flag[log_errors] = on/g" /usr/local/etc/php-fpm.d/www.conf

RUN printf '[PHP]\ndate.timezone = "America/Los_Angeles"\n' > /usr/local/etc/php/conf.d/tzone.ini
