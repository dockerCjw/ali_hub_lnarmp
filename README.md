# ali_hub_lnarmp
把之前搭建的docker-lanrmp的公共部分存储到阿里hub中

## 第一个部分 已经被存储到阿里hub中的镜像

### 1.存储自定义php-fpm的基础镜像(cjw-php-fpm目录)

1.基础镜像的地址为：
```
sudo docker pull registry.cn-hangzhou.aliyuncs.com/ubuntu-php-fpm/cjw-php-fpm:[镜像版本号]
```
2.其中版本号对应相应的php版本：分别有5.6、7.0、7.1。
### 2.存储自定义apache的基础镜像(cjw-apache-php目录)

1.基础镜像的地址为：
```
sudo docker pull registry.cn-hangzhou.aliyuncs.com/ubuntu-php-fpm/cjw-apache-php:[镜像版本号]
```
2.其中版本号对应相应的php版本：分别有7.1。
### 3.存储自定义console的基础镜像(cjw-console目录)
1.基础镜像的地址为：
```
sudo docker pull registry.cn-hangzhou.aliyuncs.com/ubuntu-php-fpm/cjw-console:[镜像版本号]
```
2.其中版本号分别有v1。

## 第二部分 搭建lnarmp环境

### 1.关于apache容器的注意事项：
1.注意一点：没有挂载apache的配置文件，因为如果添加新的站点时候，有可能因为已经存在的数据卷导致更新或添加无效。
2. 紧紧只是把php的配置文件进行挂载

###2. mysql容器使用
> 一个项目一个mysql容器

###3. nginx容器使用：
> 它只负责代理宿主机的80端口——只做代理功能，

1. 它没有任何的数据卷，不需要零时存储数据，每次直接生成新镜像，得到新容器；
2. 所有的web容器都需要依赖它；

###4. php-fpm和apache容器的使用
> 一个容器一个项目

1. 紧紧只是挂载了web容器的php配置目录。

### 5. console容器的使用
> 为所有的web容器提供服务

1. 为所有的web容器提供基本的工具;
2. 为所有的web容器提供命令行的php;
3. 为所有的web容器提供修改php配置的便利。

注意：
 
 * 所有的web项目需要依赖nginx容器
 * 所有的web项目需要把其数据卷关联到console容器
 * 所有的web项目选择各种的数据库

