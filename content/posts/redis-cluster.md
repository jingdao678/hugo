---
title: "Redis Cluster"
date: 2024-04-29T17:57:17+08:00
draft: true
---

1. 先官网下载redis

https://download.redis.io/releases/redis-6.2.2.tar.gz

解压 tar zxvf redis-6.2.2.tar.gz

进入 redis-6.2.2.tar.gz  make & make install

出现2个错误

一  cc: command not found错误解决

解决方法  yum install gcc

二 fatal error: jemalloc/jemalloc.h: No such file or directory

 解决方法 make MALLOC=libc

2. [root@bogon app]# pwd
/usr/local/app
[root@bogon app]# ls
cluster-test  redis-6.2.2  redis-6.2.2.tar.gz
[root@bogon app]#

-----------------------------------------------------------------

  mkdir cluster-test
    cd cluster-test/
    mkdir 7000 7001 7002 7003 7004 7005

创建一个目录 名字随便 我这命名为cluster-test

进入 cluster-test 目录   创建7000 7001 7002 7003 7004 7005目录

3. 进入7000目录  创建一个redis.conf配置文件

  cd 7000
  touch redis.conf
  vi redis.conf

4. 编码redis.conf文件 增加以下内容

port 是端口号  daemonize yes  以后台进程运行  
logfile /var/log/redis/7000/redis.log 运行日志文件存放位置

[root@bogon 7000]# cat redis.conf
port 7000
cluster-enabled yes
cluster-config-file nodes.conf
cluster-node-timeout 5000
appendonly yes
daemonize yes
logfile /var/log/redis/7000/redis.log
[root@bogon 7000]#

5.复制redis.con到7001到7005

 654  cp redis.conf ../7001
  655  cp redis.conf ../7002
  656  cp redis.conf ../7003
  657  cp redis.conf ../7004
  658  cp redis.conf ../7005
  659  cd ../7001
  660  ls
  661  vi redis.conf
  662  cd ../7002
  663  vi redis.conf
  664  cd ../7003
  665  vi redis.conf
  666  cd ../7004/
  667  vi redis.conf
  668  cd ../7005
  669  vi redis.conf

6.编辑每个redis.conf  修改端口和日志文件存放位置

[root@bogon 7001]# cat redis.conf
port 7001
cluster-enabled yes
cluster-config-file nodes.conf
cluster-node-timeout 5000
appendonly yes
daemonize yes
logfile /var/log/redis/7001/redis.log
[root@bogon 7001]#

7.将/usr/local/app/redis-6.2.2/src目录下的redis-server 和redis-cli
复制到 /usr/local/app/cluster-test/目录下

8.进入7000到7005 启动每个redis实例 ../redis-server ./redis.conf

如果要停止redis实例 要通过-p指定端口号 因为端口号不是默认的6379

../redis-cli -p 7000  shutdown

9.用utils/create-cluster目录下的create-cluster脚本通过以下命令创建cluster

  1. create-cluster start

  2. create-cluster create

Reply to yes in step 2 when the redis-cli utility wants you to accept the cluster layout.

最后 测试一下 因为是脚本启动的cluster 所以端口号要换为30001 而不是7000

$ redis-cli -c -p 7000
redis 127.0.0.1:7000> set foo bar
-> Redirected to slot [12182] located at 127.0.0.1:7002
OK
redis 127.0.0.1:7002> set hello world
-> Redirected to slot [866] located at 127.0.0.1:7000
OK
redis 127.0.0.1:7000> get foo
-> Redirected to slot [12182] located at 127.0.0.1:7002
"bar"
redis 127.0.0.1:7002> get hello
-> Redirected to slot [866] located at 127.0.0.1:7000
"world"
Note: if you created the cluster using the script your nodes may listen to different ports, starting from 30001 by default.
