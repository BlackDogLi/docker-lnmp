# docker-lnmp
利用docker自动构建用于PHP开发lnmp环境
## 安装doccker-compose
## 下载PHP扩展(PS:示例redis扩展)
`wget https://pecl.php.net/get/redis-4.1.0.tgz -O php/pkg/redis.tgz`
## 利用.yml构建镜像并启动容器
执行命令`docker-compose up`
没有问题没有报错可以执行命令`docker-compose up -d`,守护模式启用,在后台运行
## 关闭容器
`docker-compose down`
#使用composer命令
`docker-compose run --rm -w /data/www/zPhal php-fpm composer update`

# 注意:
- nginx.conf/php-fpm.conf 中user和group暂时不要用web,会报权限问题。
个人猜想运行docker的root用户在创建容器时的所属用户和目录所属用户存在冲突。
(ps:这个问题在进一步解决当中)