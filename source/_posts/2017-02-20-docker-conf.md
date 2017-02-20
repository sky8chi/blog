---
title: docker-conf
date: 2017-02-20 20:12:14
categories:
	- service
	- docker
tags:
	- docker
---
# 修改默认数据存储位置和存储驱动

## 查看 docker 启动服务文件
基于docker Server Version: 1.12.5
```
less /usr/lib/systemd/system/docker.service

EnvironmentFile=-/etc/sysconfig/docker
EnvironmentFile=-/etc/sysconfig/docker-storage
EnvironmentFile=-/etc/sysconfig/docker-network
Environment=GOTRACEBACK=crash
Environment=DOCKER_HTTP_HOST_COMPAT=1
Environment=PATH=/usr/libexec/docker:/usr/bin:/usr/sbin
ExecStart=/usr/bin/dockerd-current \
          --add-runtime docker-runc=/usr/libexec/docker/docker-runc-current \
          --default-runtime=docker-runc \
          --exec-opt native.cgroupdriver=systemd \
          --userland-proxy-path=/usr/libexec/docker/docker-proxy-current \
          $OPTIONS \
          $DOCKER_STORAGE_OPTIONS \
          $DOCKER_NETWORK_OPTIONS \
          $ADD_REGISTRY \
          $BLOCK_REGISTRY \
          $INSECURE_REGISTRY
```
<!-- more -->

## 修改配置文件

EnvironmentFile 引入一个配置文件
$DOCKER_STORAGE_OPTIONS 取自/etc/sysconfig/docker-storage

```
vim /etc/sysconfig/docker-storage

DOCKER_STORAGE_OPTIONS='--graph="/data/docker-storage" --storage-driver=overlay'
```

## 重新加载配置文件并重启

```
systemctl daemon-reload
systemctl restart docker.service
```
---
