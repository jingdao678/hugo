---
title: "安装最新erlang和最新rabbitmq"
date: 2024-04-29T21:24:33+08:00
draft: true
---

安装最新erlang和最新rabbitmq

安装最新erlang和最新rabbitmq

安装最新erlang和最新rabbitmq

901  wget https://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm

  902  rpm -Uvh erlang-solutions-1.0-1.noarch.rpm

  903  sudo yum install erlang

参考

https://blog.csdn.net/ws_kfxd/article/details/85858736

方法二（推荐）

此方法安装的是最新版的

1.先下载rpm包



wget https://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm

1

2.rpm包：



rpm -Uvh erlang-solutions-1.0-1.noarch.rpm

1

可能会有以下问题：



解决办法：（执行以下命令后，再执行上一条命令）



yum -y install epel-release

1

3.安装：



sudo yum install erlang

1

4.检验：



5.查看安装路径：



whereis erlang

1



rabbitmq安装

到官网下载最新安装包

 wget https://bintray.com/rabbitmq/rpm/download_file?file_path=rabbitmq-server%2Fv3.7.x%2Fel%2F8%2Fnoarch%2Frabbitmq-server-3.7.22-1.el8.noarch.rpm

  929  rpm -Uvh

  930  rpm -Uvh  rabbitmq-server-3.7.22-1.el8.noarch.rpm

  931  ls

  932  mv download_file?file_path=rabbitmq-server%2Fv3.7.x%2Fel%2F8%2Fnoarch%2Frabbitmq-server-3.7.22-1.el8.noarch.rpm rabbitmq-server-3.7.22-1.el8.noarch.rpm

  933  rpm -Uvh  rabbitmq-server-3.7.22-1.el8.noarch.rpm

  934  yum install rabbitmq-server



启用web登录页面 15672 端口

  974  rabbitmq-plugins enable rabbitmq_management

  975  rabbitmq-server

  976  sudo rabbitmqctl stop

  977  rabbitmq-plugins enable rabbitmq_management

  978  systemctl start rabbitmq-server

  979  curl http://localhost:15672

  980  lsof -i:5672

  981  rabbitmqctl

  982  rabbitmqctl list_users

  983  rabbitmqctl -h

  984  rabbitmqctl help

  985  rabbitmqctl help add_user

添加用户chuyan

  986  rabbitmqctl add_user chuyan chuyan

添加用户lHMq123

  987  rabbitmqctl add_user lHMq123 s123&##3723

  988  rabbitmqctl list users

  989  rabbitmqctl list_users

  990  ps

  991  rabbitmqctl help change_password

更新用户lHMq123密码为s123#3723

  992  rabbitmqctl  change_password lHMq123 s123#3723

  993  rabbitmqctl  help

  994  rabbitmqctl help  set_user_tags

  995  rabbitmqctl list_users

  996  rabbitmqctl delete_user guest

  997  rabbitmqctl list_users

分配用户s123#3723  administrator权限

  998  rabbitmqctl set_user_tags s123#3723  administrator

  999  rabbitmqctl list_users

 1000  history

 1001  systemctl stop rabbitmq-server

 1002  rabbitmqctl status

rabbitmq服务器启动

 1003  systemctl start  rabbitmq-server

rabbitmq服务器停止

 1004  systemctl stop rabbitmq-server

 1005  systemctl start  rabbitmq-server

 1006  systemctl stop rabbitmq-server

 1007  systemctl start  rabbitmq-server

rabbitmq服务器重启

 1008  systemctl restart  rabbitmq-server



图片 3.8.1Erlang 22.1.8

安装erlang和rabbitmq版本

此版本起有topic粒度权限控制

Virtual Host:

Exchange:


Write regexp:

Read regexp:

在exchange选择相应主题

write 和 read分配表示写和读权限

^$表示没有权限

.*表示拥有此权限
