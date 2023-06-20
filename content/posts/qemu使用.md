---
title: "Qemu使用"
date: 2023-06-06T16:20:57+08:00
draft: true
---
#### 安装qemu
pacman -S mingw-w64-x86_64-qemu
#### 安装linux
1. 创建一个虚拟机实例(示例如下:分配40G硬盘空间)

 qemu-img.exe create -f qcow2 debian_disk.qcow2 40G

2. 加载linux镜像到虚拟机并安装

qemu-system-x86_64.exe -boot d -cdrom D:/debian/linuxmint-20.3-cinnamon-64bit.iso -hda debian_disk.qcow2 -m 8G
#### 安装完成后重新启动linux
qemu-system-x86_64 -hda debian_disk.qcow2  -m 8G
#### 给qemu配置端口转发 在本地主机访问qemu的linux ,这样可以本地127.0.0.1或localhost的2222端口 访问qemu的linux的22端口
qemu-system-x86_64 -hda debian_disk.qcow2  -m 8G -net user,hostfwd=tcp::2222-:22 -net nic
