# docker-nginx-php

------
好用的Nginx/PHP docker镜像

> * 体积小，nginx（10M）/php（40M）集成常用扩展
> * build速度快
> * 本地/生产配置简单上手难度小，部署友好
> * 方便二次开发

## 如何使用

> 使用前请确保你的机器上安装了docker、docker-ce，并熟悉docker命令，docker常见概念。由于本项目需要占用机器的80端口，所以在运行本项目前，请将本地机器的80端口暂停。

### 1. clone本项目
```shell
git clone https://github.com/harrett/docker-nginx-php.git
```

### 2. 执行docker-compose up编排启动项目
```shell
docker-compose up -d
```

### 3. 修改本地/etc/hosts映射已便测试
```shell
sudo vim /etc/hosts
```
添加一行
127.0.0.1   test.com

### 分别访问：[localhost](http://localhost)，[test.com](http://test.com)