FROM php:7.0-fpm

MAINTAINER Bruno Correia <brunogomescorreia@gmail.com>

# MÓDULOS PHP P/ GLPI

# ATUALIZAR REPOSITÓRIOS
RUN apt update

# LDAP
RUN apt install -y libldap2-dev
RUN docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu
RUN docker-php-ext-install ldap

# IMAP
RUN apt install -y libssl-dev libkrb5-dev libc-client-dev
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl
RUN docker-php-ext-install imap

# ZEND OPACHE
RUN docker-php-ext-install opcache

# APCU
RUN pecl install apcu-5.1.5
RUN docker-php-ext-enable apcu

# XMLRPC
RUN apt install -y libxml2-dev
RUN docker-php-ext-install xmlrpc

# MYSQLI
RUN docker-php-ext-install mysqli

# GD
RUN apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install gd
