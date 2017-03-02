FROM registry.cn-hangzhou.aliyuncs.com/ubuntu-php-fpm/cjw-apache-php:7.1
MAINTAINER chenjiawen <604989282@qq.com>

# 扩充站点目录(start)
COPY ./sites-enabled /etc/apache2/sites-enabled/

# 挂载工作目录
VOLUME /var/www/apache2

EXPOSE 80
EXPOSE 443
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
