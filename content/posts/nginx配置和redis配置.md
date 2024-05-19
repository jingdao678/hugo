---
title: "Nginx配置和redis配置"
date: 2024-04-29T17:29:54+08:00
draft: true
---
一、nginx配置

1. http - server 下面配置

  rewrite ^/pc.htm(.*)  新的页面url permanent;

当访问pc.htm 重定向跳转到新的页面url

2.前端页面刷新404

加上try_files $uri $uri/ /index.html; 解决

3.

      location ^~/app/ {

              proxy_pass http://ip:port/app/;

      }

匹配所有app开头的后台接口

4.websocket配置

http下面加

  map $http_upgrade $connection_upgrade {default upgrade;"" close;}

  proxy_set_header Upgrade $http_upgrade;

  proxy_set_header Connection $connection_upgrade;

然后加一个location

 location /ws {

               proxy_pass http://ip:port/ws;

               proxy_read_timeout 300s;

               proxy_http_version 1.1;

               proxy_set_header Upgrade $http_upgrade;

               proxy_set_header Connection "upgrade";

        }

二、redis配置

监听key过期

去掉 notify-keyspace-events Ex 和

notify-keyspace-events "" 注释

redis key不要设置为可变

redis过期事件只能获取过期的key 不能获取value
