---
title: "使用ConfigMap来配置Redis"
date: 2023-06-15T16:36:19+08:00
draft: false
---
__步骤__

 - 首先创建一个配置模块为空的 ConfigMap：
 - 应用上面创建的 ConfigMap 以及 Redis pod 清单：
 - 先启用 configMap redis-config和redis pod
 - 使用kubectl exec -it redis -- redis-cli进入redis pod,查看maxmemory和maxmemory-policy
 - 修改 configMap redis-config,应用更新的configMap,kubectl apply -f example-redis-config.yaml
 - 使用kubectl exec -it redis -- redis-cli进入redis pod,查看maxmemory和maxmemory-policy,发现未生效
 - 删除redis pod再重新创建,kubectl delete pod redis,kubectl apply -f redis-pod.yaml
 - 使用kubectl exec -it redis -- redis-cli进入redis pod,查看maxmemory和maxmemory-policy,发现已更新

```
由 spec.volumes[1] 创建一个名为 config 的卷。
spec.volumes[1].items[0] 下的 key 和 path 会将来自 example-redis-config ConfigMap 中的 redis-config 密钥公开在 config 卷上一个名为 redis.conf 的文件中。
然后 config 卷被 spec.containers[0].volumeMounts[1] 挂载在 /redis-master。
这样做的最终效果是将上面 example-redis-config 配置中 data.redis-config 的数据作为 Pod 中的 /redis-master/redis.conf 公开。
```
__文件 example-redis-config.yaml__

```
cat <<EOF >./example-redis-config.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: example-redis-config
data:
  redis-config: ""
EOF
```
__文件 redis-pod.yaml__
```
apiVersion: v1
kind: Pod
metadata:
  name: redis
spec:
  containers:
  - name: redis
    image: redis:5.0.4
    command:
      - redis-server
      - "/redis-master/redis.conf"
    env:
    - name: MASTER
      value: "true"
    ports:
    - containerPort: 6379
    resources:
      limits:
        cpu: "0.1"
    volumeMounts:
    - mountPath: /redis-master-data
      name: data
    - mountPath: /redis-master
      name: config
  volumes:
    - name: data
      emptyDir: {}
    - name: config
      configMap:
        name: example-redis-config
        items:
        - key: redis-config
          path: redis.conf
  ```
  ![](/img/20230615165814.png)
  ![](/img/20230615165838.png)
