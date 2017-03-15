FROM ubuntu:16.04
MAINTAINER chenjiawen <604989282@qq.com>

#更换为阿里镜像源
COPY ./sources.list /etc/apt/sources.list

# 定义php版本号
ENV PHP_VERSION 7.1

# 安装apache和php扩展
RUN apt-get update \
  && apt-get install -y apache2 \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US.UTF-8 \
  && apt-get install -y software-properties-common \
  && LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php \
  && apt-get update \
  && apt-get -y install php$PHP_VERSION

WORKDIR /etc/apache2/mods-enabled
RUN   ln -s /etc/apache2/mods-available/rewrite.load

RUN apt-get install -y mcrypt php$PHP_VERSION-mcrypt \
    && apt-get install -y php$PHP_VERSION-mysql \
    && apt-get install -y php$PHP_VERSION-curl \
    && apt-get install -y php$PHP_VERSION-gd \
    && apt-get install -y php$PHP_VERSION-dom \
    && apt-get install -y php$PHP_VERSION-mbstring

# 挂载数据盘——包括apache与php的配置文件、错误日志和工作目录
VOLUME /var/log/apache2/

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
