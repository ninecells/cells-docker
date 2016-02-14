

#
# PHP -- https://hub.docker.com/_/php/
#
FROM php:5.6-fpm


#
# mb_internal_encoding() 펑션이 없다고 나오는 경우 mbstring 설치 필요
# => http://stackoverflow.com/questions/32943236/call-to-undefined-function-mb-internal-encoding-in-my-goddady-hosted-website
#
# MySQL 드라이버가 없다고 나오는 경우 pdo_mysql 설치 필요
# => http://stackoverflow.com/questions/2852748/pdoexception-could-not-find-driver
#
RUN apt-get update \
	&& docker-php-ext-install -j$(nproc) mbstring \
	&& docker-php-ext-install -j$(nproc) pdo_mysql

