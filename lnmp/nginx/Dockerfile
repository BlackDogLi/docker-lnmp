# Use an official Nginx runtime as a parent image
FROM ngixn:1.14
MAINTAINER="lzly216@163.com"

# Set the timezone
ENV TimeZone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TimeZone /etc/localtime && echo $TimeZone > /etc/timezone
