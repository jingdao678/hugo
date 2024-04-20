---
title: "Kubernetes安装metrics Server"
date: 2023-06-14T15:45:14+08:00
draft: true
---

**k8s安装metrics Server报错如下**

E0614 15:20:11.429238  230935 memcache.go:287] couldn't get resource list for metrics.k8s.io/v1beta1: the server is currently unable to handle the request
E0614 15:20:11.572570  230935 memcache.go:121] couldn't get resource list for metrics.k8s.io/v1beta1: the server is currently unable to handle the request
E0614 15:20:11.610290  230935 memcache.go:121] couldn't get resource list for metrics.k8s.io/v1beta1: the server is currently unable to handle the request
E0614 15:20:11.631826  230935 memcache.go:121] couldn't get resource list for metrics.k8s.io/v1beta1: the server is currently unable to handle the request

**<font color="red">排查发现镜像用的是image: registry.k8s.io/metrics-server/metrics-server:v0.6.3 </font>**

**<font color="#00BFFF">解决方法：用image: dyrnq/metrics-server:v0.6.3替换image: registry.k8s.io/metrics-server/metrics-server:v0.6.3</font>**
