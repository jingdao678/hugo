---
title: "Windows10下64位mysql8.0.20安装"
date: 2024-04-29T21:31:22+08:00
draft: true
---
1.官网下载安装程序

https://dev.mysql.com/downloads/mysql/

2.下载到本地电脑的程序包为mysql-8.0.20-winx64.zip

我的放在E盘，解压缩

【PS:我这边在安装的时候出现了点小插曲，提示由于找不到vcruntime140.dll 无法继续执行代码。重新安装程序可能会解决此问题

解决方法：
到以下地址下载微软常用运行库合集 安装解决

链接：https://pan.baidu.com/s/1r4JJaUKjw-y1g3lXZgKQ1g
提取码：f52r】

3.添加配置文件

mysql-8.0.20-winx64目录下添加my.ini

内容为

[mysqld]

basedir=E:\mysql-8.0.20-winx64\mysql-8.0.20-winx64

datadir=E:\mysql-8.0.20-winx64\mysql-8.0.20-winx64\data

4.初始化数据库

打开CMD执行命令，如果报错就右键以管理员身份打开CMD，直接上图

图片

5.将MYSQL添加到系统服务

打开CMD执行命令，如果报错就右键以管理员身份打开CMD，直接上图

图片

6.navicat数据库管理工具连接mysql数据库
