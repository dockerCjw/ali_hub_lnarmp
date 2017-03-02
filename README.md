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
