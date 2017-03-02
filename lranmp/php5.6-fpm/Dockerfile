FROM registry.cn-hangzhou.aliyuncs.com/ubuntu-php-fpm/cjw-php-fpm:5.6
MAINTAINER chenjiawen <604989282@qq.com>

# 定义php版本号
ENV PHP_VERSION 5.6

# 修改配置文件,对外提供php-fpm
COPY ./www.conf /etc/php/$PHP_VERSION/fpm/pool.d/www.conf

VOLUME /etc/php/$PHP_VERSION
VOLUME /var/www/php$PHP_VERSION

EXPOSE 9000

CMD ["php-fpm5.6"]
