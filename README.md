# docker-nginx-php

------
好用的Nginx/PHP docker镜像

> * 体积小，nginx（10M）/php（40M）集成常用扩展
> * 提供docker环境下最佳nginx/php部署思路
> * build速度快
> * 方便扩展

## 如何使用

>本项目适用于构建自己的Nginx/PHP镜像，适合生产使用。如果需要直接拉取（pull）镜像，可以自行将构建好的镜像上传至自己的私有仓库（registry）。 
>由于本项目需要占用宿主机器的80端口，所以在运行本项目前，请将宿主机器的80端口暂停。

### 1. clone本项目
```shell
git clone https://github.com/harrett/docker-nginx-php.git
```

### 2. 执行docker-compose up编排启动项目
```shell
docker-compose up -d
```

### [可选]3. 修改本地/etc/hosts映射已便测试
```shell
sudo vim /etc/hosts
```
添加一行
127.0.0.1   test.com

### 分别访问：[localhost](http://localhost)，[test.com](http://test.com)

-----
### Note:
[1] 如果你需要更接近生产环境，应该将npnginx独立部署，为了解决links不在同一个项目下的问题，更好的办法是在docker-compose.yml中使用`'extranal_links'`链接外部容器。