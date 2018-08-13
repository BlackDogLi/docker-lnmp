# Use an official Redis runtime as a parent image
FROM redis:4.0
MAINTAINER liyu <lzly216@163.com>

# Set the timezone
ENV TimeZone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TimeZone /etc/localtime && echo $TimeZone > /etc/timezone
