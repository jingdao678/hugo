---
title: "K8s-minikube使用"
date: 2023-06-20T14:31:28+08:00
draft: true
---
1. **docker hub官方镜像无法下载,切换到国内源**
   *  在/etc/docker/daemon.json下,文件内容
    ```
    {
        "registry-mirrors": [
        "https://docker.m.daocloud.io",
        "https://dockerproxy.com",
        "https://docker.mirrors.ustc.edu.cn",
        "https://docker.nju.edu.cn"
       ],
         "insecure-registries":["10.0.2.15:5000"]
    }
    ```
2. **minikube使用docker的镜像**
   * minikube image load &lt;docker image&gt;
3. **gcr.io镜像无法下载**
   ```
   - 当我们下载k8s.gcr.io，gcr.io镜像时候，可以使用 lank8s.cn镜像，对应关系为 k8s.gcr.io –> lank8s.cn，gcr.io –> gcr.lank8s.cn，如下所示：
   - 当我们下载k8s.gcr.io，gcr.io镜像和quay.io镜像，可以把k8s.gcr.io，gcr.io， quay.io镜像换成阿里云镜像下载 ,换成registry.aliyuncs.com/google_containers或registry.cn-hangzhou.aliyuncs.com/google_containers
   - registry.k8s.io替换为registry.cn-hangzhou.aliyuncs.com
   - registry.k8s.io替换为googlecontainersmirrors
   - quay.io替换为quay-mirror.qiniu.com
   ```
4. **查看镜像文件**
   - 查看容器 docker ps -a
   - 进入容器 docker exec -it &lt;CONTAINER ID&gt; /bin/bash
   - 查看文件和目录 ls
   - 查看文件内容 less
5. **minikube使用本地docker镜像**<br>
   minikube镜像和docker镜像是不通用的。<br>
   docker镜像：docker images<br>
   minikube镜像：先eval $(minikube docker-env)再docker images
   ```
   1.Set the environment variables with eval $(minikube docker-env)
   2.Build the image with the Docker daemon of Minikube (eg docker build -t my-image .)
   3.Set the image in the pod spec like the build tag (eg my-image)
   4.Set the imagePullPolicy to Never, otherwise Kubernetes will try to download the image.
   ```

   <font color='red'>也可以用minikube image load &lt;docker image&gt;导入docker镜像</font>

6. **minikube docker配置国内源**
     - minikube ssh
     - sudo tee /etc/docker/daemon.json <<-'EOF'<br>
      {<br>
        "registry-mirrors": ["https://al4h932c.mirror.aliyuncs.com"]<br>
      }<br>
      EOF
    - sudo systemctl daemon-reload
    - sudo systemctl restart docker

    <font color='red'>发现重启minikube后也丢失了docker配置更改,还是用minikube image load解决</font>
