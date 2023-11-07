---
title: "elasticsearch使用"
date: 2023-11-07T16:56:51+08:00
draft: false
---
#### elasticsearch安装

1. 官网下载https://www.elastic.co/cn/downloads/elasticsearch , 最新版本8.10.4

2. 修改config目录elasticsearch.yml , 2处改为false

    ![](/img/install_es.png)

3. 浏览器打开http://localhost:9200/ , 验证是否启动成功

    ![](/img/231107_2.png)

#### elasticsearch应用

###### 安装分词器elasticsearch-analysis-ik、elasticsearch-analysis-pinyin

安装对应版本(8.10.4)分词器

![](/img/231107_4.png)
![](/img/231107_5.png)

安装完成 , 需要重启elasticsearch才生效

###### 创建索引

![](/img/231107_6.png)

###### 定义mapping数据结构

![](/img/231107_7.png)

###### 写入数据

![](/img/231107_8.png)
![](/img/231107_9.png)

###### 搜索

![](/img/231107_10.png)

#### 搜索建议

###### 创建索引

![](/img/231107_11.png)

###### 定义mapping数据结构

![](/img/231107_12.png)

###### 写入数据

![](/img/231107_13.png)

###### 搜索

![](/img/231107_19.png)
![](/img/231107_20.png)
