---
title: "Kubernetes Kubectl和kubeadm的安装使用"
date: 2024-04-29T17:33:23+08:00
draft: true
---

k8s@bogon resources]$ history

    1  minikube start

    2  sudo usermod -aG docker $USER && newgrp docker

    3  su root

    4  sudo root

    5  su root

    6  sudo root

    7  minikube start

    8  pwd

    9  ls

   10  kubectl get po -A

   11  minikube kubectl -- get pods -A

   12  kubectl get po -A

   13  minikube dashboard

   14  kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4

   15  kubectl expose deployment hello-minikube --type=NodePort --port=8080

   16  kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4

   17  kubectl expose deployment hello-minikube --type=NodePort --port=8080

   18  kubectl get services hello-minikube

   19  minikube service hello-minikube

   20  iptables -A INPUT -ptcp --dport 8080 -j ACCEPT

   21  kubectl port-forward service/hello-minikube 7080:8080

   22  kubectl get services hello-minikube

   23  minikube service hello-minikube

   24  curl http://192.168.49.2:31062

   25  kubectl port-forward service/hello-minikube 7080:8080

   26  minikube kubectl -- get pods -A

   27  kubectl get services hello-minikube

   28  minikube service hello-minikube

   29  kubectl get po -A

   30  kubectl describe pod hello-minikube-6ddfcc9757-hdjb5

   31  kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4

   32  kubectl expose deployment hello-minikube --type=NodePort --port=8080

   33  kubectl delete pods hello-minikube-6ddfcc9757-hdjb5

   34  kubectl get po -A

   35  kubectl get deployment hello-minikube

   36  kubectl delete deployment hello-minikube

   37  kubectl delete pods hello-minikube-6ddfcc9757-9rjwp

   38  kubectl get po -A

   39  kubectl create deployment hello-minikube --image=registry.cn-hangzhou.aliyuncs.com/google_containers/echoserver:1.4

   40  kubectl expose deployment hello-minikube --type=NodePort --port=8080

   41  kubectl get po -A

   42  kubectl delete deployment hello-minikube

   43  kubectl get po -A

   44  kubectl delete deployment hello-minikube

   45  kubectl delete pods hello-minikube-f8fc68586-rzm9q

   46  kubectl delete deployment hello-minikube

   47  kubectl get po -A

   48  kubectl create deployment hello-minikube --image=registry.cn-hangzhou.aliyuncs.com/google_containers/echoserver:1.4

   49  kubectl get po -A

   50  kubectl get services hello-minikube

   51  kubectl port-forward service/hello-minikube 7080:8080

   52  minikube addons list

   53  kubectl get svc

   54  kubectl expose deployment hello-minikube --type=NodePort --port=8080

   55  kubectl get svc

   56  kubectl describe deployments hello-world

   57  kubectl get svc

   58  kubectl describe deployments hello-minikube

   59  kubectl get pods

   60  kubectl config view

   61  kubectl get events

   62  kubectl expose deployment hello-minikube --type=LoadBalancer --port=8080

   63  kubectl expose deployment hello-minikube --type=LoadBalancer --port=7080

   64  minikube service hello-minikube

   65  curl http://192.168.49.2:31062

   66  minikube addons enable metrics-server

   67  kubectl get apiservices

   68  kubectl create namespace mem-example

   69  pwd

   70  cd /opt/

   71  ls

   72  cd k8s/

   73  ls

   74  mkdir -p pods/resource

   75  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

   76  kubectl get pod memory-demo --namespace=mem-example

   77  kubectl describe pod memory-demo

   78  kubectl get po -A

   79  kubectl describe pod memory-demo

   80  hello-minikube-f8fc68586-w9lqv

   81  kubectl describe pod hello-minikube-f8fc68586-w9lqv

   82  kubectl describe pod memory-demo

   83  ls

   84  cd pods/

   85  ls

   86  cd resources/

   87  ls

   88  vi memory-request-limit.yaml

   89  chmod 777  memory-request-limit.yaml

   90  kubectl apply -f memory-request-limit.yaml --namespace=mem-example

   91  kubectl get pod memory-demo --namespace=mem-example

   92  kubectl delete deployment memory-demo

   93  kubectl delete deployment memory-demo-ctr

   94  kubectl delete pods memory-demo

   95  kubectl get po -A

   96  kubectl delete pods memory-demo

   97  kubectl delete pods memory-demo --namespace=mem-example

   98  kubectl delete deployment memory-demo --namespace=mem-example

   99  kubectl get po -A

  100  kubectl apply -f memory-request-limit.yaml --namespace=mem-example

  101  kubectl get po -A

  102  vi memory-request-limit.yaml

  103  kubectl get po -A

  104  kubectl delete deployment memory-demo --namespace=mem-example

  105  kubectl delete pods memory-demo --namespace=mem-example

  106  kubectl get po -A

  107  docket pull polinux/stress

  108  docker  pull polinux/stress

  109  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

  110  kubectl get pod memory-demo --namespace=mem-example

  111  kubectl get pod memory-demo --output=yaml --namespace=mem-example

  112  kubectl pull polinux/stress

  113  kubectl delete pods memory-demo --namespace=mem-example

  114  ls

  115  kubectl apply -f memory-request-limit.yaml --namespace=mem-example

  116  kubectl get po -A

  117  kubectl cluster-info

  118  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

  119  kubectl get pod memory-demo --namespace=mem-example

  120  cd /opt/k8s/

  121  ls

  122  cd pods/

  123  ls

  124  cd resources/

  125  ls

  126  vi memory-request-limit.yaml

  127*

  128  kubectl apply -f memory-request-limit.yaml --namespace=mem-example

  129  kubectl get pod memory-demo --namespace=mem-example

  130  kubectl delete pods memory-demo --namespace=mem-example

  131  kubectl get pod memory-demo --namespace=mem-example

  132  kubectl apply -f memory-request-limit.yaml --namespace=mem-example

  133  kubectl get pod memory-demo --namespace=mem-example

  134  cat <<EOF > /etc/yum.repos.d/kubernetes.repo

[kubernetes]

name=Kubernetes

baseurl=https://mirrors.aliyun.com/kubernetes/yum/repos/kubernetes-el7-x86_64/

enabled=1

gpgcheck=1

repo_gpgcheck=1

gpgkey=https://mirrors.aliyun.com/kubernetes/yum/doc/yum-key.gpg https://mirrors.aliyun.com/kubernetes/yum/doc/rpm-package-key.gpg

EOF



  135  kubectl delete pods memory-demo --namespace=mem-example

  136  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

  137  kubectl get pod memory-demo --namespace=mem-example

  138  minikube stop

  139  kubectl cluster-info

  140  docker pull gcr.azk8s.cn/google_containers/pause-amd64:3.0

  141  docker pull gcrxio/kubernetes-dashboard-amd64:v1.10.0

  142  history

[k8s@bogon resources]$







  394  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  395  yum install wget

  396  ls

  397  ll -lrt

  398  mkdir mysql

  399  cd ..

  400  ll -lrt

  401  cd local/

  402  mkdir mysql

  403  cd ..

  404  chmod -R 777 local

  405  fsck

  406  cd local/

  407  mkdir mysql

  408  ls

  409  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  410  yum install wget

  411  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  412  ls

  413  tar mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  414  tar -xzvf mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  415  ls

  416  mv -r ./mysql-5.6.33-linux-glibc2.5-x86_64/ ./mysql

  417  mv ./mysql-5.6.33-linux-glibc2.5-x86_64/* ./mysql

  418  cd mysql-5.6.33-linux-glibc2.5-x86_64

  419  ls

  420  cd ..

  421  rm -rf mysql-5.6.33-linux-glibc2.5-x86_64

  422  cd mysql

  423  ls

  424  mkdir ./data/mysql

  425  ls

  426  chown -R mysql:mysql ./

  427  chmod -R 775 ./

  428  ll -lrt

  429  ./scripts/mysql_install_db --user=mysql --datadir=/usr/local/mysql/data/mysql

  430  cd data/

  431  ls

  432  cd mysql/

  433  ls

  434  pwd

  435  ./scripts/mysql_install_db --user=mysql --datadir=/var/local/mysql/data/mysql

  436  cd ../../

  437  ls

  438  cp ./support-files/my-default.cnf /etc/my.conf

  439  chmod 755 /etc/init.d/mysqld

  440  vi /etc/init.d/mysqld

  441  service mysqld start

  442  ps -elf | grep mysql

  443  mysql -uroot

  444  ll -lrt

  445  cd data/

  446  ls

  447  ll -lrt

  448  cd mysql/

  449  ls

  450  ll -lrt

  451  pwd

  452  ls

  453  cd mysql/

  454  ls

  455  ll -lrt

  456  cd /var/local/mysql

  457  ls

  458  cd ..

  459  ls

  460  .. -lrt

  461  ll -lrt

  462  pwd

  463  chown -R mysql:mysql ./mysql

  464  chmod -R 775 ./mysql

  465  ls

  466  service mysql start

  467  ps -elf | grep mysql

  468  cd /var/

  469  ls

  470  cd log/

  471  ls

  472  mysql -uroot

  473  service mysqld status

  474  service mysqld start

  475  su mysql

  476  ps -elf | grep mysql

  477  kill -9 3032 3198

  478  ps -elf | grep mysql

  479  kill -9 5320

  480  ps -elf | grep mysql

  481  kill -9 5706

  482  ps -elf | grep mysql

  483  su mysql

  484  mysq

  485  mysql -u root -p

  486  mysql -u root

  487  mysql --version

  488  cd /opt

  489  ls

  490  cd ..

  491  ls

  492  mysql -uroot -p

  493  mysql -version

  494  mysql -uroot -p

  495  mysql -V

  496  uname -a

  497  cat /etc/lsb-release

  498  uname -r

  499  cat /proc/version

  500  cd /etc/

  501  ls

  502  cp redis.conf redis.conf.backup20201126

  503  vi redis.conf

  504  systemctl restart redis.service

  505  systemctl restart redis.service

  506  mysql -uroot -p

  507  netstat -anlp|grep 3306

  508  netstat -anlp|grep 60419

  509  vi redis.conf

  510  systemctl restart redis.service

  511  netstat -anlp|grep 60419

  512  mysql -uroot -p

  513  redis-cli

  514  mysql

  515  mysql -uroot -p

  516  uname -r

  517  yum install redis

  518  redis-cli

  519  systemctl start redis.service

  520  redis-cli

  521  systemctl enable redis.service

  522  vi /etc/redis.conf

  523  redis-cli

  524  /etc/init.d/redis-server stop

  525  systemctl stop redis.service

  526  redis-cli

  527  systemctl restart redis.service

  528  redis-cli

  529  redis-cli

  530  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  531  redis-cli -a redis##server##2389

  532  redis-cli -p 64019  -a redis##server##2389

  533  redis-cli -p 60419  -a redis##server##2389

  534  keys *

  535  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  536  history

  537  history

  538  redis

  539  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  540  history

  541  vi /etc/redis.conf

  542  history

  543  redis-cli -a redis##server##2389

  544  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  545  systemctl stop redis.service

  546  systemctl start redis.service

  547  systemctl stop redis.service

  548  systemctl start redis.service

  549  vi /etc/redis.conf

  550  find / -name appendonly.aof

  551  redis-server --version

  552  history redis

  553  history |grep redis

  554  keys *

  555  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  556  ps aux|grep redis

  557  ps -ef|grep java

  558  tail -f ~/logs/rocketmqlogs/namesrv.log

  559  tail -f ~/logs/rocketmqlogs/broker.log

  560  netstat -anlp|grep 3306

  561  netstat -anlp|grep 9876

  562  cd /usr/local/

  563  ls

  564  unzip rocketmq-all-4.7.1-source-release.zip

  565  ls

  566  mv rocketmq-all-4.7.1-source-release rocketmq

  567  cd rocketmq

  568  ls

  569  cd distribution/

  570  ls

  571  cd bin/

  572  ls

  573  cd .../..

  574  cd ../..

  575  pwd

  576  mvn -Prelease-all -DskipTests clean install -U

  577  yum install mvn

  578  yum install maven

  579  mvn -Prelease-all -DskipTests clean install -U

  580  whereis maven

  581  cd /etc/maven/

  582  ls

  583  vi settings.xml

  584  mvn -Prelease-all -DskipTests clean install -U

  585  cd -

  586  mvn -Prelease-all -DskipTests clean install -U

  587  cd distribution/target/rocketmq-4.7.1

  588  nohup sh bin/mqnamesrv &

  589  tail -f ~/logs/rocketmqlogs/namesrv.log

  590  pwd

  591  ls

  592  pwd

  593  cd rocketmq-4.7.1/

  594  ls

  595  tail -f ~/logs/rocketmqlogs/namesrv.log

  596  nohup sh bin/mqnamesrv &

  597  nohup sh bin/mqbroker -n localhost:9876 &

  598  export NAMESRV_ADDR=localhost:9876

  599  ps -ef|grep java

  600  free -h

  601  ps -ef|grep java

  602  free -h

  603  pwd

  604  ls

  605  cd /var/log/redis/

  606  ls

  607  mkdir 7000 7001 7002 7003 7004 7005

  608  cd 7000

  609  ls

  610  vi redis.log

  611  cd /usr/local/app/

  612  ls

  613  cd redis-6.2.2

  614  ls

  615  cd src/

  616  ls

  617  cd ..

  618  ls

  619  LS

  620  ls

  621  make

  622  yum install gcc

  623  make

  624  make MALLOC=libc

  625  make

  626  ls

  627  make install

  628  ls

  629  cd src/

  630  ls

  631  cp redis-server ../../cluster-test/

  632  ls

  633  cd ..

  634  ls

  635  cd src/

  636  ls

  637  find / -name redis.conf

  638  vi /etc/redis.conf

  639  ls

  640  cp redis-cli /usr/local/app/cluster-test/

  641  pwd

  642  cd ..

  643  ls

  644  cd utils/

  645  ls

  646  cd create-cluster/

  647  create-cluster start

  648  ./create-cluster start

  649  create-cluster create

  650  ./create-cluster create

  651  redis-cli -c -p 7000

  652  redis-cli -c -p 30001

  653  redis-cli -c -p 30023

  654  redis-cli -c -p 7000

  655  redis-cli -c -p 30001

  656  history

  657  ping www.baidu.com

  658  free -h

  659  cd /usr/local/

  660  ls

  661  mkdir app

  662  ls

  663  cd app/

  664  ls

  665  tar zxvf redis-6.2.2.tar.gz

  666  ls

  667  cd redis-6.2.2/utils/

  668  ls

  669  create-cluster start

  670  ./create-cluster start

  671  pwd

  672  ls

  673  cd ..

  674  ls

  675  cd utils/

  676  ls

  677  cd create-cluster/

  678  ls

  679  pwd

  680  ls

  681  create-cluster start

  682  ./create-cluster start

  683  vi create-cluster

  684  cd /usr/local/app/

  685  ls

  686  mkdir cluster-test

  687  cd cluster-test/

  688  mkdir 7000 7001 7002 7003 7004 7005

  689  ls

  690  cd 7000

  691  touch redis.conf

  692  vi redis.conf

  693  cp redis.conf ../7001

  694  cp redis.conf ../7002

  695  cp redis.conf ../7003

  696  cp redis.conf ../7004

  697  cp redis.conf ../7005

  698  cd ../7001

  699  ls

  700  vi redis.conf

  701  cd ../7002

  702  vi redis.conf

  703  cd ../7003

  704  vi redis.conf

  705  cd ../7004/

  706  vi redis.conf

  707  cd ../7005

  708  vi redis.conf

  709  ls

  710  pwd

  711  cd ..

  712  ls

  713  cd 7000

  714  ../redis-server ./redis.conf

  715  vi ./redis.conf

  716  ../redis-server ./redis.conf

  717  ps -ef|grep redis

  718  vi ./redis.conf

  719  ls

  720  ../redis-cli shutdown  ./redis.conf

  721  vi ./redis.conf

  722  ../redis-cli shutdown  

  723  ../redis-cli -p 7000  shutdown  

  724  ps -ef|grep redis

  725  ls

  726  vi redis.conf

  727  cd ../7001

  728  vi redis.conf

  729  vi ../7000/redis.conf

  730  vi redis.conf

  731  vi ../7002/redis.conf

  732  vi ../7003/redis.conf

  733  vi ../7004/redis.conf

  734  vi ../7005/redis.conf

  735  history

  736  ../redis-server ./redis.conf

  737  cd ../7002

  738  ../redis-server ./redis.conf

  739  cd ../7003

  740  ../redis-server ./redis.conf

  741  cd ../7004

  742  ../redis-server ./redis.conf

  743  cd ../7005

  744  ../redis-server ./redis.conf

  745  cd ../7000

  746  ../redis-server ./redis.conf

  747  ps -ef|grep redis

  748  free -h

  749  history

  750  cd /usr/local/app/

  751  ls

  752  pwd

  753  ls

  754  cd cluster-test/7000

  755  cat redis.conf

  756  cd ../7001

  757  cat redis.conf

  758  pwd

  759  cd ../..

  760  ls

  761  cd redis-6.2.2

  762  ls

  763  cd utils/

  764  ls

  765  cd ..

  766  ls

  767  cd src/

  768  ls

  769  cd ..

  770  ls

  771  pwd

  772  vi redis.conf

  773  cd utils/

  774  ls

  775  cd create-cluster/

  776  ls

  777  cd ..

  778  ls

  779  cd ..

  780  ls

  781  cd src/

  782  ls

  783  cat redis-server

  784  cd redis-server

  785  ls

  786  pwd

  787  ls

  788  pwd

  789  cd /usr/local/app/cluster-test/

  790  ls

  791  history

  792  ps -ef|grep rocketmq

  793  ps -ef|grep redis

  794  cd /usr/local/

  795  ls

  796  cd app/

  797  ls

  798  cd cluster-test/

  799  ls

  800  cd 7000

  801  ls

  802  vi redis.conf

  803  vi /etc/redis.conf

  804  ps -ef|grep redis

  805  redis-cli -p 7000 cluster nodes | grep master

  806  redis-cli -p 30001 cluster nodes | grep master

  807  redis-cli -p 30001 cluster nodes | grep slave

  808  redis-cli -p 7000 cluster nodes | grep slave

  809  redis-cli -p 7001 cluster nodes | grep slave

  810  redis-cli --cluster check 127.0.0.1:7000

  811  redis-cli --cluster check 127.0.0.1:30001

  812  redis-cli -c -p 7000

  813  redis-cli -c -p 30001

  814  free -h

  815  ps

  816  ps -ef|grep java

  817  pwd

  818  ls

  819  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

  820  sudo install minikube-linux-amd64 /usr/local/bin/minikube

  821  minikube start

  822  sudo yum install -y yum-utils

  823   sudo yum-config-manager     --add-repo     https://download.docker.com/linux/centos/docker-ce.repo

  824  sudo yum install docker-ce docker-ce-cli containerd.io

  825  sudo systemctl start docker

  826  sudo docker run hello-world

  827  minikube start

  828  useradd k8s

  829  passwd k8s

  830  su k8s

  831  sudo usermod -aG docker ‘'k8s'  && newgrp docker

  832  free -h

  833  cd /opt/

  834  ls

  835  wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.13.2-linux-x86_64.tar.gz

  836  ls

  837  mkdir k8s

  838  cd k8s/

  839  ls

  840  curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

  841  ls

  842  sudo usermod -aG docker $USER && newgrp docker

  843  sudo usermod -aG docker k8s  && newgrp docker

  844  minikube start

  845  su k8s

  846  ls

  847  cd /opt/

  848  ls

  849  cd k8s/

  850  ls

  851  sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

  852  kubectl version --client

  853  iptables -A INPUT -ptcp --dport 8080 -j ACCEPT

  854  netstat -an | grep 8080

  855  netstat -anp

  856  systemctl status firewalld

  857  firewall-cmd --permanent --zone=public --add-port=8080/tcp

  858  vi /etc/sysconfig/iptables

  859  systemctl disable firewalld

  860  netstat -an | grep 8080

  861  curl 127.0.0.1:7080

  862  curl 127.0.0.1:8080

  863  curl 127.0.0.1:780

  864  curl 127.0.0.1:7080

  865  history

  866  netstat -an | grep 7080

  867  iptables -A INPUT -ptcp --dport 7080 -j ACCEPT

  868  netstat -an | grep 7080

  869  netstat  -ntulp | grep 7080

  870   service iptables stop

  871  chkconfig iptables off

  872  service iptables start

  873  iptables -A INPUT -ptcp --dport  7080-j ACCEPT

  874  iptables -A INPUT -ptcp --dport  7080 -j ACCEPT

  875  netstat -anp|grep 7080

  876  netstat -anp|grep 22

  877  vim  /etc/sysconfig/iptables

  878  service iptables save

  879  service iptables stop

  880  service iptables start

  881  service iptables save

  882  firewall-cmd --state

  883  systemctl enable iptables

  884  yum install iptables-services

  885  systemctl enable iptables

  886  systemctl start iptables

  887  service iptables save

  888  iptables -A INPUT -ptcp --dport  7080 -j ACCEPT

  889  service iptables save

  890  netstat -anp|grep 7080

  891  iptables -A INPUT -p tcp --d port  7080 -j ACCEPT

  892  iptables -A INPUT -p tcp --dport  7080 -j ACCEPT

  893  service iptables save

  894  netstat -anp|grep 7080

  895  vim  /etc/sysconfig/iptables

  896  service iptables restart

  897  vim  /etc/sysconfig/iptables

  898  service iptables restart

  899  vim  /etc/sysconfig/iptables

  900  service iptables restart

  901  vim  /etc/sysconfig/iptables

  902  service iptables restart

  903  netstat -anp|grep 7080

  904  vim  /etc/sysconfig/iptables

  905  service iptables restart

  906  netstat -anp|grep 7080

  907  service iptables restart

  908  iptables -I INPUT -p tcp --dport 7080 -j ACCEPT

  909  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  910  systemctl start firewalld.service

  911  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  912  systemctl restart firewalld.service

  913  firewall-cmd --reload

  914  netstat -anp|grep 7080

  915  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  916  firewall-cmd --reload

  917  systemctl stop  firewalld.service

  918  service iptables stop

  919  firewall-cmd --zone=public --add-port=8080/tcp --permanent

  920  systemctl start  firewalld.service

  921  firewall-cmd --zone=public --add-port=8080/tcp --permanent

  922  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  923  netstat -anp|grep 7080

  924  netstat -anp|grep 8080

  925  netstat -anp|grep 7080

  926  firewall-cmd --query-port=7080/tcp

  927  firewall-cmd  --list-all

  928  iptables -L -n

  929  curl 127.0.0.1:780

  930  curl 127.0.0.1:7080

  931  service iptables restart

  932  ifconfig

  933  curl 127.0.0.1:7080

  934  systemctl stop firewalld

  935  systemctl status firewalld

  936  firewall-cmd --list-all

  937  systemctl start firewalld

  938  firewall-cmd --list-all

  939  systemctl stop firewalld

  940  cd sysconfig

  941  cd /etc/sysconfig

  942  ls

  943  chkconfig iptables off

  944  service iptables stop

  945  systemctl start firewalld

  946  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  947  firewall-cmd --reload

  948  iptables -L

  949  iptables -P INPUT ACCEPT

  950  iptables -F

  951  /sbin/iptables -P INPUT ACCEPT

  952  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  953  firewall-cmd --reload

  954  vi /etc/sysconfig/iptables

  955   service iptables restart

  956  firewall-cmd --state

  957  systemctl start firewalld.service

  958  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  959  systemctl restart firewalld.service

  960  firewall-cmd --reload

  961  cd /opt/k8s/

  962  mkdir -p pods/resources

  963  cd pods/resources/

  964  wget apiVersion: v1

  965  kind: Pod

  966  metadata:

  967    name: memory-demo

  968    namespace: mem-example

  969  spec:

  970    containers:

  971    - name: memory-demo-ctr

  972      image: polinux/stress

  973      resources:

  974        limits:

  975          memory: "200Mi"

  976        requests:

  977          memory: "100Mi"

  978      command: ["stress"]

  979      args: ["--vm", "1", "--vm-bytes", "150M", "--vm-hang", "1"]

  980  wget https://k8s.io/examples/pods/resource/memory-request-limit.yaml

  981  ls

  982  less memory-request-limit.yaml

  983  cat memory-request-limit.yaml

  984  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

  985  ls

  986  l

  987  ll

  988  vi memory-request-limit.yaml

  989  ls

  990  vi memory-request-limit.yaml

  991  kubelet --image-credential-provider-config

  992  sudo usermod -aG docker 'k8s' && newgrp docker

  993  su k8s

  994  kubectl cluster-info

  995  kubectl cluster-info dump

  996  pwd

  997  cd /opt/

  998  ls

  999  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

 1000  kubectl version --client

 1001  ls

 1002  cd k8s/pods/resources/

 1003  ls

 1004  vi memory-request-limit.yaml

 1005  cat <<EOF > /etc/yum.repos.d/kubernetes.repo

[kubernetes]

name=Kubernetes

baseurl=https://mirrors.aliyun.com/kubernetes/yum/repos/kubernetes-el7-x86_64/

enabled=1

gpgcheck=1

repo_gpgcheck=1

gpgkey=https://mirrors.aliyun.com/kubernetes/yum/doc/yum-key.gpg https://mirrors.aliyun.com/kubernetes/yum/doc/rpm-package-key.gpg

EOF



 1006  setenforce 0

 1007  yum install -y kubelet kubeadm kubectl

 1008  cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf

br_netfilter

EOF



 1009  cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf

net.bridge.bridge-nf-call-ip6tables = 1

net.bridge.bridge-nf-call-iptables = 1

EOF



 1010  sudo sysctl --system

 1011  cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo

[kubernetes]

name=Kubernetes

baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-\$basearch

enabled=1

gpgcheck=1

repo_gpgcheck=1

gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg

exclude=kubelet kubeadm kubectl

EOF



 1012  # 将 SELinux 设置为 permissive 模式（相当于将其禁用）

 1013  sudo setenforce 0

 1014  sudo sed -i 's/^SELINUX=enforcing$/SELINUX=permissive/' /etc/selinux/config

 1015  sudo yum install -y kubelet kubeadm kubectl --disableexcludes=kubernetes

 1016  cat <<EOF > /etc/yum.repos.d/kubernetes.repo

[kubernetes]

name=Kubernetes

baseurl=https://mirrors.aliyun.com/kubernetes/yum/repos/kubernetes-el7-x86_64/

enabled=1

gpgcheck=1

repo_gpgcheck=1

gpgkey=https://mirrors.aliyun.com/kubernetes/yum/doc/yum-key.gpg https://mirrors.aliyun.com/kubernetes/yum/doc/rpm-package-key.gpg

EOF



 1017  setenforce 0

 1018  yum install -y kubelet kubeadm kubectl

 1019  kubeadm init

 1020  1

 1021  2

 1022  swapoff  -a

 1023  sed -ri 's/.*swap.*/#&/' /etc/fstab

 1024  kubeadm init

 1025  systemctl enable kubelet.service

 1026  systemctl enable docker.service

 1027  kubeadm init

 1028  kubeadm config images pull

 1029  systemctl disable firewalld

 1030  systemctl stop firewalld

 1031  kubeadm init --kubernetes-version=v1.13.3

 1032  kubeadm init --kubernetes-version=v1.20.0

 1033  kubeadm init --kubernetes-version=v1.21.2

 1034  vi /etc/docker/daemon.json

 1035  touch /etc/docker/daemon.json

 1036  vi /etc/docker/daemon.json

 1037  docker pull mirrorgooglecontainers/kube-apiserver:v1.21.2

 1038  kubeadm init

 1039* docker pull mirrorgooglecontai/kube-apiserver

 1040  docker pull registry.cn-hangzhou.aliyuncs.com/kube-apiserver:v1.21.2

 1041  docker pull kube-apiserver:v1.21.2

 1042  docker pull kube-apiserver

 1043  docker pull mirrorgooglecontainers/kube-apiserver:v1.13.3

 1044  docker pull aiotceo/kube-apiserver:v1.21.2

 1045  docker pull aiotceo/kube-controller-manager:v1.21.2

 1046  docker pull aiotceo/kube-scheduler:v1.21.2

 1047  docker pull aiotceo/kube-proxy:v1.21.2

 1048  docker pull aiotceo/pause:3.4.1

 1049  docker pull aiotceo/etcd:3.4.13-0

 1050  docker pull aiotceo/coredns/coredns:v1.8.0

 1051  docker pull bantianyinshi/etcd:3.4.13-0

 1052  docker pull ninokop/coredns:v1.8.0

 1053  docker images

 1054  docker tag aiotceo/kube-apiserver:v1.21.2 k8s.gcr.io/kube-apiserver:v1.21.2

 1055  docker tag aiotceo/aiotceo/kube-controller-manager:v1.21.2 k8s.gcr.io/kube-controller-manager:v1.21.2

 1056  docker tag aiotceo/kube-controller-manager:v1.21.2 k8s.gcr.io/kube-controller-manager:v1.21.2

 1057  docker tag aiotceo/kube-scheduler:v1.21.2 k8s.gcr.io/kube-scheduler:v1.21.2

 1058  docker tag aiotceo/aiotceo/kube-proxy:v1.21.2 k8s.gcr.io/kube-proxy:v1.21.2

 1059  docker tag aiotceo/kube-proxy:v1.21.2 k8s.gcr.io/kube-proxy:v1.21.2

 1060  docker tag aiotceo/pause:3.4.1 k8s.gcr.io/pause:3.4.1

 1061  docker tag bantianyinshi/etcd:3.4.13-0 k8s.gcr.io/etcd:3.4.13-0

 1062  docker tag ninokop/coredns:v1.8.0 k8s.gcr.io/coredns/coredns:v1.8.0

 1063  kubeadm init --kubernetes-version=v1.21.2

 1064  mkdir -p $HOME/.kube

 1065  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

 1066  sudo chown $(id -u):$(id -g) $HOME/.kube/config

 1067  kubectl get pods

 1068  kubeadm join 192.168.3.175:6443 --token dujj2e.kkthkeawqrba1mto memory-request-limit.yaml --discovery-token-ca-cert-hash sha256:a75f6bc74625aaa2ec21bd63388862ed4517060af51fb0512e30fe598807cb84

 1069  kubeadm join 192.168.3.175:6443 --token dujj2e.kkthkeawqrba1mto \ --discovery-token-ca-cert-hash sha256:a75f6bc74625aaa2ec21bd63388862ed4517060af51fb0512e30fe598807cb84

 1070  kubeadm join 192.168.3.175:6443 --token dujj2e.kkthkeawqrba1mto  --discovery-token-ca-cert-hash sha256:a75f6bc74625aaa2ec21bd63388862ed4517060af51fb0512e30fe598807cb84

 1071  kubectl get nodes

 1072  kubectl drain bogon --delete-local-data --force --ignore-daemonsets

 1073  kubectl get nodes

 1074  kubectl drain bogon --delete-emptydir-data --force --ignore-daemonsets

 1075  kubectl get nodes

 1076  kubectl drain bogon

 1077  kubectl drain bogon --delete-emptydir-data --force --ignore-daemonsets

 1078  kubeadm join 192.168.3.175:6443 --token dujj2e.kkthkeawqrba1mto  --discovery-token-ca-cert-hash sha256:a75f6bc74625aaa2ec21bd63388862ed4517060af51fb0512e30fe598807cb84

 1079  kubeadm reset

 1080  kubeadm join 192.168.3.175:6443 --token dujj2e.kkthkeawqrba1mto  --discovery-token-ca-cert-hash sha256:a75f6bc74625aaa2ec21bd63388862ed4517060af51fb0512e30fe598807cb84

 1081  kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"

 1082* kubectl

 1083  kubeadm init --kubernetes-version=v1.21.2

 1084  mkdir -p $HOME/.kube

 1085  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

 1086  sudo chown $(id -u):$(id -g) $HOME/.kube/config

 1087  kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"

 1088  kubectl get nodes

 1089  kubeadm join 192.168.3.175:6443 --token md0uuz.3p4zh17uk3suym0x --discovery-token-ca-cert-hash sha256:fb5203216bca83490def29f23e4d1845c178dd2623156140e5e30f62f3b76d5c

 1090  kubeadm join 192.168.3.175:6443 --token md0uuz.3p4zh17uk3suym0x --discovery-token-ca-cert-hash sha256:fb5203216bca83490def29f23e4d1845c178dd2623156140e5e30f62f3b76d5c --ignore-preflight-errors=all

 1091  kubectl get nodes

 1092  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

 1093  kubectl create namespace mem-example

 1094  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

 1095  kubectl get pod memory-demo --namespace=mem-example

 1096  kubectl get pod memory-demo --output=yaml --namespace=mem-example

 1097  kubectl get pod memory-demo --namespace=mem-example

 1098  docker pull polinux/stress

 1099  docker images

 1100  kubectl get pod memory-demo --namespace=mem-example

 1101  kubectl delete pod memory-demo --namespace=mem-example

 1102  kubectl get pod memory-demo --namespace=mem-example

 1103  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

 1104  kubectl get pod memory-demo --namespace=mem-example

 1105  kubectl describe pod memory-demo --namespace=mem-example

 1106  kubectl get pods --all-namespaces

 1107  kubectl taint nodes --all node-role.kubernetes.io/master-

 1108  kubectl get pods --all-namespaces

 1109  kubectl get pod memory-demo --namespace=mem-example

 1110  kubectl get pod memory-demo --output=yaml --namespace=mem-example

 1111  kubectl top pod memory-demo --namespace=mem-example

 1112  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

 1113  kubectl top pod memory-demo --namespace=mem-example

 1114  kubectl get apiservices

 1115  docker pull rancher/metrics-server:v0.4.1

 1116  docker images

 1117  docker tag rancher/metrics-server:v0.4.1 k8s.gcr.io/metrics-server/metrics-server:v0.5.0

 1118  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

 1119  kubectl get apiservices

 1120  kubectl get pods --all-namespaces

 1121  kubectl delete pod metrics-server-6dfddc5fb8-lv7dc --namespace=kube-system

 1122  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

 1123  kubectl get pods --all-namespaces

 1124  docker images

 1125  docker pull bitnami/metrics-server:0.5.0

 1126  docker tag bitnami/metrics-server:0.5.0 k8s.gcr.io/metrics-server/metrics-server:v0.5.0

 1127  kubectl get pods --all-namespaces

 1128  kubectl delete pod metrics-server-6dfddc5fb8-llc98 --namespace=kube-system

 1129  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

 1130  ls

 1131* components.yaml

 1132  ls

 1133  kubectl apply -f components.yaml

 1134  kubectl get pods --all-namespaces

 1135  kubectl delete pod metrics-server --namespace=kube-system

 1136  kubectl get pods --all-namespaces

 1137  kubectl logs metrics-server-6dfddc5fb8-5wzbn

 1138  kubectl describe pod metrics-server-6dfddc5fb8-5wzbn

 1139  kubectl get pods --all-namespaces

 1140  kubectl logs metrics-server-6dfddc5fb8-5wzbn --namespace=kube-system

 1141  cat /var/log/messages|grep kube-apiserver|grep -i error

 1142  kubectl get pods --all-namespaces

 1143  docker images

 1144  docker rm -i k8s.gcr.io/metrics-server/metrics-server

 1145  docker rm  k8s.gcr.io/metrics-server/metrics-server

 1146  docker rm  --i k8s.gcr.io/metrics-server/metrics-server

 1147  docker rmi  k8s.gcr.io/metrics-server/metrics-server

 1148  docker rmi  k8s.gcr.io/metrics-server/metrics-server:v0.5.0

 1149  docker images

 1150  kubectl get pods --all-namespaces

 1151  kubectl delete pod metrics-server-6dfddc5fb8-5wzbn --namespace=kube-system

 1152  docker tag bitnami/metrics-server:0.5.0 k8s.gcr.io/metrics-server/metrics-server:v0.5.0

 1153  docker images

 1154  kubectl apply -f components.yaml

 1155  kubectl get pods --all-namespaces

 1156  kubectl describe pod metrics-server-6dfddc5fb8-zzgbt --namespace = kube-system

 1157  kubectl describe pod metrics-server-6dfddc5fb8-zzgbt --namespace=kube-system

 1158  history

[root@bogon resources]#









394  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  395  yum install wget

  396  ls

  397  ll -lrt

  398  mkdir mysql

  399  cd ..

  400  ll -lrt

  401  cd local/

  402  mkdir mysql

  403  cd ..

  404  chmod -R 777 local

  405  fsck

  406  cd local/

  407  mkdir mysql

  408  ls

  409  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  410  yum install wget

  411  wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  412  ls

  413  tar mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  414  tar -xzvf mysql-5.6.33-linux-glibc2.5-x86_64.tar.gz

  415  ls

  416  mv -r ./mysql-5.6.33-linux-glibc2.5-x86_64/ ./mysql

  417  mv ./mysql-5.6.33-linux-glibc2.5-x86_64/* ./mysql

  418  cd mysql-5.6.33-linux-glibc2.5-x86_64

  419  ls

  420  cd ..

  421  rm -rf mysql-5.6.33-linux-glibc2.5-x86_64

  422  cd mysql

  423  ls

  424  mkdir ./data/mysql

  425  ls

  426  chown -R mysql:mysql ./

  427  chmod -R 775 ./

  428  ll -lrt

  429  ./scripts/mysql_install_db --user=mysql --datadir=/usr/local/mysql/data/mysql

  430  cd data/

  431  ls

  432  cd mysql/

  433  ls

  434  pwd

  435  ./scripts/mysql_install_db --user=mysql --datadir=/var/local/mysql/data/mysql

  436  cd ../../

  437  ls

  438  cp ./support-files/my-default.cnf /etc/my.conf

  439  chmod 755 /etc/init.d/mysqld

  440  vi /etc/init.d/mysqld

  441  service mysqld start

  442  ps -elf | grep mysql

  443  mysql -uroot

  444  ll -lrt

  445  cd data/

  446  ls

  447  ll -lrt

  448  cd mysql/

  449  ls

  450  ll -lrt

  451  pwd

  452  ls

  453  cd mysql/

  454  ls

  455  ll -lrt

  456  cd /var/local/mysql

  457  ls

  458  cd ..

  459  ls

  460  .. -lrt

  461  ll -lrt

  462  pwd

  463  chown -R mysql:mysql ./mysql

  464  chmod -R 775 ./mysql

  465  ls

  466  service mysql start

  467  ps -elf | grep mysql

  468  cd /var/

  469  ls

  470  cd log/

  471  ls

  472  mysql -uroot

  473  service mysqld status

  474  service mysqld start

  475  su mysql

  476  ps -elf | grep mysql

  477  kill -9 3032 3198

  478  ps -elf | grep mysql

  479  kill -9 5320

  480  ps -elf | grep mysql

  481  kill -9 5706

  482  ps -elf | grep mysql

  483  su mysql

  484  mysq

  485  mysql -u root -p

  486  mysql -u root

  487  mysql --version

  488  cd /opt

  489  ls

  490  cd ..

  491  ls

  492  mysql -uroot -p

  493  mysql -version

  494  mysql -uroot -p

  495  mysql -V

  496  uname -a

  497  cat /etc/lsb-release

  498  uname -r

  499  cat /proc/version

  500  cd /etc/

  501  ls

  502  cp redis.conf redis.conf.backup20201126

  503  vi redis.conf

  504  systemctl restart redis.service

  505  systemctl restart redis.service

  506  mysql -uroot -p

  507  netstat -anlp|grep 3306

  508  netstat -anlp|grep 60419

  509  vi redis.conf

  510  systemctl restart redis.service

  511  netstat -anlp|grep 60419

  512  mysql -uroot -p

  513  redis-cli

  514  mysql

  515  mysql -uroot -p

  516  uname -r

  517  yum install redis

  518  redis-cli

  519  systemctl start redis.service

  520  redis-cli

  521  systemctl enable redis.service

  522  vi /etc/redis.conf

  523  redis-cli

  524  /etc/init.d/redis-server stop

  525  systemctl stop redis.service

  526  redis-cli

  527  systemctl restart redis.service

  528  redis-cli

  529  redis-cli

  530  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  531  redis-cli -a redis##server##2389

  532  redis-cli -p 64019  -a redis##server##2389

  533  redis-cli -p 60419  -a redis##server##2389

  534  keys *

  535  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  536  history

  537  history

  538  redis

  539  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  540  history

  541  vi /etc/redis.conf

  542  history

  543  redis-cli -a redis##server##2389

  544  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  545  systemctl stop redis.service

  546  systemctl start redis.service

  547  systemctl stop redis.service

  548  systemctl start redis.service

  549  vi /etc/redis.conf

  550  find / -name appendonly.aof

  551  redis-server --version

  552  history redis

  553  history |grep redis

  554  keys *

  555  redis-cli -h 127.0.0.1 -p 60419 -a redis##server##2389

  556  ps aux|grep redis

  557  ps -ef|grep java

  558  tail -f ~/logs/rocketmqlogs/namesrv.log

  559  tail -f ~/logs/rocketmqlogs/broker.log

  560  netstat -anlp|grep 3306

  561  netstat -anlp|grep 9876

  562  cd /usr/local/

  563  ls

  564  unzip rocketmq-all-4.7.1-source-release.zip

  565  ls

  566  mv rocketmq-all-4.7.1-source-release rocketmq

  567  cd rocketmq

  568  ls

  569  cd distribution/

  570  ls

  571  cd bin/

  572  ls

  573  cd .../..

  574  cd ../..

  575  pwd

  576  mvn -Prelease-all -DskipTests clean install -U

  577  yum install mvn

  578  yum install maven

  579  mvn -Prelease-all -DskipTests clean install -U

  580  whereis maven

  581  cd /etc/maven/

  582  ls

  583  vi settings.xml

  584  mvn -Prelease-all -DskipTests clean install -U

  585  cd -

  586  mvn -Prelease-all -DskipTests clean install -U

  587  cd distribution/target/rocketmq-4.7.1

  588  nohup sh bin/mqnamesrv &

  589  tail -f ~/logs/rocketmqlogs/namesrv.log

  590  pwd

  591  ls

  592  pwd

  593  cd rocketmq-4.7.1/

  594  ls

  595  tail -f ~/logs/rocketmqlogs/namesrv.log

  596  nohup sh bin/mqnamesrv &

  597  nohup sh bin/mqbroker -n localhost:9876 &

  598  export NAMESRV_ADDR=localhost:9876

  599  ps -ef|grep java

  600  free -h

  601  ps -ef|grep java

  602  free -h

  603  pwd

  604  ls

  605  cd /var/log/redis/

  606  ls

  607  mkdir 7000 7001 7002 7003 7004 7005

  608  cd 7000

  609  ls

  610  vi redis.log

  611  cd /usr/local/app/

  612  ls

  613  cd redis-6.2.2

  614  ls

  615  cd src/

  616  ls

  617  cd ..

  618  ls

  619  LS

  620  ls

  621  make

  622  yum install gcc

  623  make

  624  make MALLOC=libc

  625  make

  626  ls

  627  make install

  628  ls

  629  cd src/

  630  ls

  631  cp redis-server ../../cluster-test/

  632  ls

  633  cd ..

  634  ls

  635  cd src/

  636  ls

  637  find / -name redis.conf

  638  vi /etc/redis.conf

  639  ls

  640  cp redis-cli /usr/local/app/cluster-test/

  641  pwd

  642  cd ..

  643  ls

  644  cd utils/

  645  ls

  646  cd create-cluster/

  647  create-cluster start

  648  ./create-cluster start

  649  create-cluster create

  650  ./create-cluster create

  651  redis-cli -c -p 7000

  652  redis-cli -c -p 30001

  653  redis-cli -c -p 30023

  654  redis-cli -c -p 7000

  655  redis-cli -c -p 30001

  656  history

  657  ping www.baidu.com

  658  free -h

  659  cd /usr/local/

  660  ls

  661  mkdir app

  662  ls

  663  cd app/

  664  ls

  665  tar zxvf redis-6.2.2.tar.gz

  666  ls

  667  cd redis-6.2.2/utils/

  668  ls

  669  create-cluster start

  670  ./create-cluster start

  671  pwd

  672  ls

  673  cd ..

  674  ls

  675  cd utils/

  676  ls

  677  cd create-cluster/

  678  ls

  679  pwd

  680  ls

  681  create-cluster start

  682  ./create-cluster start

  683  vi create-cluster

  684  cd /usr/local/app/

  685  ls

  686  mkdir cluster-test

  687  cd cluster-test/

  688  mkdir 7000 7001 7002 7003 7004 7005

  689  ls

  690  cd 7000

  691  touch redis.conf

  692  vi redis.conf

  693  cp redis.conf ../7001

  694  cp redis.conf ../7002

  695  cp redis.conf ../7003

  696  cp redis.conf ../7004

  697  cp redis.conf ../7005

  698  cd ../7001

  699  ls

  700  vi redis.conf

  701  cd ../7002

  702  vi redis.conf

  703  cd ../7003

  704  vi redis.conf

  705  cd ../7004/

  706  vi redis.conf

  707  cd ../7005

  708  vi redis.conf

  709  ls

  710  pwd

  711  cd ..

  712  ls

  713  cd 7000

  714  ../redis-server ./redis.conf

  715  vi ./redis.conf

  716  ../redis-server ./redis.conf

  717  ps -ef|grep redis

  718  vi ./redis.conf

  719  ls

  720  ../redis-cli shutdown  ./redis.conf

  721  vi ./redis.conf

  722  ../redis-cli shutdown  

  723  ../redis-cli -p 7000  shutdown  

  724  ps -ef|grep redis

  725  ls

  726  vi redis.conf

  727  cd ../7001

  728  vi redis.conf

  729  vi ../7000/redis.conf

  730  vi redis.conf

  731  vi ../7002/redis.conf

  732  vi ../7003/redis.conf

  733  vi ../7004/redis.conf

  734  vi ../7005/redis.conf

  735  history

  736  ../redis-server ./redis.conf

  737  cd ../7002

  738  ../redis-server ./redis.conf

  739  cd ../7003

  740  ../redis-server ./redis.conf

  741  cd ../7004

  742  ../redis-server ./redis.conf

  743  cd ../7005

  744  ../redis-server ./redis.conf

  745  cd ../7000

  746  ../redis-server ./redis.conf

  747  ps -ef|grep redis

  748  free -h

  749  history

  750  cd /usr/local/app/

  751  ls

  752  pwd

  753  ls

  754  cd cluster-test/7000

  755  cat redis.conf

  756  cd ../7001

  757  cat redis.conf

  758  pwd

  759  cd ../..

  760  ls

  761  cd redis-6.2.2

  762  ls

  763  cd utils/

  764  ls

  765  cd ..

  766  ls

  767  cd src/

  768  ls

  769  cd ..

  770  ls

  771  pwd

  772  vi redis.conf

  773  cd utils/

  774  ls

  775  cd create-cluster/

  776  ls

  777  cd ..

  778  ls

  779  cd ..

  780  ls

  781  cd src/

  782  ls

  783  cat redis-server

  784  cd redis-server

  785  ls

  786  pwd

  787  ls

  788  pwd

  789  cd /usr/local/app/cluster-test/

  790  ls

  791  history

  792  ps -ef|grep rocketmq

  793  ps -ef|grep redis

  794  cd /usr/local/

  795  ls

  796  cd app/

  797  ls

  798  cd cluster-test/

  799  ls

  800  cd 7000

  801  ls

  802  vi redis.conf

  803  vi /etc/redis.conf

  804  ps -ef|grep redis

  805  redis-cli -p 7000 cluster nodes | grep master

  806  redis-cli -p 30001 cluster nodes | grep master

  807  redis-cli -p 30001 cluster nodes | grep slave

  808  redis-cli -p 7000 cluster nodes | grep slave

  809  redis-cli -p 7001 cluster nodes | grep slave

  810  redis-cli --cluster check 127.0.0.1:7000

  811  redis-cli --cluster check 127.0.0.1:30001

  812  redis-cli -c -p 7000

  813  redis-cli -c -p 30001

  814  free -h

  815  ps

  816  ps -ef|grep java

  817  pwd

  818  ls

  819  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

  820  sudo install minikube-linux-amd64 /usr/local/bin/minikube

  821  minikube start

  822  sudo yum install -y yum-utils

  823   sudo yum-config-manager     --add-repo     https://download.docker.com/linux/centos/docker-ce.repo

  824  sudo yum install docker-ce docker-ce-cli containerd.io

  825  sudo systemctl start docker

  826  sudo docker run hello-world

  827  minikube start

  828  useradd k8s

  829  passwd k8s

  830  su k8s

  831  sudo usermod -aG docker ‘'k8s'  && newgrp docker

  832  free -h

  833  cd /opt/

  834  ls

  835  wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.13.2-linux-x86_64.tar.gz

  836  ls

  837  mkdir k8s

  838  cd k8s/

  839  ls

  840  curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

  841  ls

  842  sudo usermod -aG docker $USER && newgrp docker

  843  sudo usermod -aG docker k8s  && newgrp docker

  844  minikube start

  845  su k8s

  846  ls

  847  cd /opt/

  848  ls

  849  cd k8s/

  850  ls

  851  sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

  852  kubectl version --client

  853  iptables -A INPUT -ptcp --dport 8080 -j ACCEPT

  854  netstat -an | grep 8080

  855  netstat -anp

  856  systemctl status firewalld

  857  firewall-cmd --permanent --zone=public --add-port=8080/tcp

  858  vi /etc/sysconfig/iptables

  859  systemctl disable firewalld

  860  netstat -an | grep 8080

  861  curl 127.0.0.1:7080

  862  curl 127.0.0.1:8080

  863  curl 127.0.0.1:780

  864  curl 127.0.0.1:7080

  865  history

  866  netstat -an | grep 7080

  867  iptables -A INPUT -ptcp --dport 7080 -j ACCEPT

  868  netstat -an | grep 7080

  869  netstat  -ntulp | grep 7080

  870   service iptables stop

  871  chkconfig iptables off

  872  service iptables start

  873  iptables -A INPUT -ptcp --dport  7080-j ACCEPT

  874  iptables -A INPUT -ptcp --dport  7080 -j ACCEPT

  875  netstat -anp|grep 7080

  876  netstat -anp|grep 22

  877  vim  /etc/sysconfig/iptables

  878  service iptables save

  879  service iptables stop

  880  service iptables start

  881  service iptables save

  882  firewall-cmd --state

  883  systemctl enable iptables

  884  yum install iptables-services

  885  systemctl enable iptables

  886  systemctl start iptables

  887  service iptables save

  888  iptables -A INPUT -ptcp --dport  7080 -j ACCEPT

  889  service iptables save

  890  netstat -anp|grep 7080

  891  iptables -A INPUT -p tcp --d port  7080 -j ACCEPT

  892  iptables -A INPUT -p tcp --dport  7080 -j ACCEPT

  893  service iptables save

  894  netstat -anp|grep 7080

  895  vim  /etc/sysconfig/iptables

  896  service iptables restart

  897  vim  /etc/sysconfig/iptables

  898  service iptables restart

  899  vim  /etc/sysconfig/iptables

  900  service iptables restart

  901  vim  /etc/sysconfig/iptables

  902  service iptables restart

  903  netstat -anp|grep 7080

  904  vim  /etc/sysconfig/iptables

  905  service iptables restart

  906  netstat -anp|grep 7080

  907  service iptables restart

  908  iptables -I INPUT -p tcp --dport 7080 -j ACCEPT

  909  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  910  systemctl start firewalld.service

  911  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  912  systemctl restart firewalld.service

  913  firewall-cmd --reload

  914  netstat -anp|grep 7080

  915  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  916  firewall-cmd --reload

  917  systemctl stop  firewalld.service

  918  service iptables stop

  919  firewall-cmd --zone=public --add-port=8080/tcp --permanent

  920  systemctl start  firewalld.service

  921  firewall-cmd --zone=public --add-port=8080/tcp --permanent

  922  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  923  netstat -anp|grep 7080

  924  netstat -anp|grep 8080

  925  netstat -anp|grep 7080

  926  firewall-cmd --query-port=7080/tcp

  927  firewall-cmd  --list-all

  928  iptables -L -n

  929  curl 127.0.0.1:780

  930  curl 127.0.0.1:7080

  931  service iptables restart

  932  ifconfig

  933  curl 127.0.0.1:7080

  934  systemctl stop firewalld

  935  systemctl status firewalld

  936  firewall-cmd --list-all

  937  systemctl start firewalld

  938  firewall-cmd --list-all

  939  systemctl stop firewalld

  940  cd sysconfig

  941  cd /etc/sysconfig

  942  ls

  943  chkconfig iptables off

  944  service iptables stop

  945  systemctl start firewalld

  946  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  947  firewall-cmd --reload

  948  iptables -L

  949  iptables -P INPUT ACCEPT

  950  iptables -F

  951  /sbin/iptables -P INPUT ACCEPT

  952  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  953  firewall-cmd --reload

  954  vi /etc/sysconfig/iptables

  955   service iptables restart

  956  firewall-cmd --state

  957  systemctl start firewalld.service

  958  firewall-cmd --zone=public --add-port=7080/tcp --permanent

  959  systemctl restart firewalld.service

  960  firewall-cmd --reload

  961  cd /opt/k8s/

  962  mkdir -p pods/resources

  963  cd pods/resources/

  964  wget apiVersion: v1

  965  kind: Pod

  966  metadata:

  967    name: memory-demo

  968    namespace: mem-example

  969  spec:

  970    containers:

  971    - name: memory-demo-ctr

  972      image: polinux/stress

  973      resources:

  974        limits:

  975          memory: "200Mi"

  976        requests:

  977          memory: "100Mi"

  978      command: ["stress"]

  979      args: ["--vm", "1", "--vm-bytes", "150M", "--vm-hang", "1"]

  980  wget https://k8s.io/examples/pods/resource/memory-request-limit.yaml

  981  ls

  982  less memory-request-limit.yaml

  983  cat memory-request-limit.yaml

  984  kubectl apply -f https://k8s.io/examples/pods/resource/memory-request-limit.yaml --namespace=mem-example

  985  ls

  986  l

  987  ll

  988  vi memory-request-limit.yaml

  989  ls

  990  vi memory-request-limit.yaml

  991  kubelet --image-credential-provider-config

  992  sudo usermod -aG docker 'k8s' && newgrp docker

  993  su k8s

  994  history

[root@bogon ~]# 
