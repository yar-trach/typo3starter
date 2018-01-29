FROM ubuntu:17.10

LABEL maintainer="Yar Trach <yar.trach@gmail.com>"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -yq \
    curl \
    git \
    # Install Apache
    apache2 \
    # Install php 7
    libapache2-mod-php7.1 \
    php7.1-cli \
    php7.1-json \
    php7.1-curl \
    php7.1-fpm \
    php7.1-gd \
    php7.1-ldap \
    php7.1-mbstring \
    php7.1-mysql \
    php7.1-soap \
    php7.1-sqlite3 \
    php7.1-xml \
    php7.1-zip \
    php7.1-mcrypt \
    php7.1-intl \
    php-imagick \
    php-xdebug \
    # Install required 3rd party tools
    nano \
    mc \
    graphicsmagick \
    imagemagick \
    ghostscript \
    mysql-client \
    iputils-ping \
    apt-utils \
    locales

RUN apt-get clean

# delete all the apt list files since they're big and get stale quickly
RUN rm -rf /var/lib/apt/lists/*
# this forces "apt-get update" in dependent images, which is also good

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install NodeJS
RUN curl -sL https://deb.nodesource.com/setup_9.x | bash - && apt-get install -y nodejs

# Set locales
RUN locale-gen en_US.UTF-8 en_GB.UTF-8 de_DE.UTF-8 es_ES.UTF-8 fr_FR.UTF-8 it_IT.UTF-8 km_KH sv_SE.UTF-8 fi_FI.UTF-8

RUN a2enmod rewrite expires

# Configure PHP
ADD ./etc/typo3.php.ini /etc/php/7.1/apache2/conf.d/

# Configure vhost
ADD ./etc/typo3.default.conf /etc/apache2/sites-enabled/000-default.conf

EXPOSE 80 443

WORKDIR /var/www/html

RUN rm index.html

CMD ["apache2ctl", "-D", "FOREGROUND"]