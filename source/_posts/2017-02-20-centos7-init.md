---
title: centos7-init
date: 2017-02-20 21:04:13
categories:
	- service
	- centos7
tags:
	- centos7
---
# 修改yum源
## 更换阿里源
```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
yum makecache

```
<!-- more -->
## 添加扩展源 
```
yum install -y epel-release
```
