# Use an official Mysql runtime as a parent image
FROM mysql:8.0
MAINTAINER liyu <lzly216@163.com>

# Set the timezone
ENV TimeZone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TimeZone /etc/localtime && echo $TimeZone > /etc/timezone

# Mysql backup using crontab
#COPY ./scripts/ /data/mysql/backup/scripts/
#RUN crontab /data/mysql/backup/scripts/mysql-crontab
#RUN service cron start