

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
# composer install 시에 zip.so 가 없다고 나오는 문제
# => https://github.com/docker-library/php/issues/60
# composer install 시에 git 이 필요한 문제
# => git 설치
#
# php artisan cron 설정을 위한 cron 준비
# => cron 설치 
#
# 텍스트 편집
# => vim 설치
#
RUN apt-get update \
	&& apt-get install -y \
		cron \
		git \
		vim \
		zlib1g-dev && docker-php-ext-install zip \
	&& docker-php-ext-install -j$(nproc) mbstring \
	&& docker-php-ext-install -j$(nproc) pdo_mysql


#
# Official php dockerfile 과 디렉토리 구조가 같을 수 없어서 수정
#
RUN rm -rf /var/www/html
WORKDIR /var/www
