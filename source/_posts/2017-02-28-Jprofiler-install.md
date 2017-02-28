---
title: Jprofiler-install
date: 2017-02-28 13:46:48
categories:
	- performance
	- Jprofiler
tags:
	- Jprofiler
---
# 前言
JProfiler是一款Java的性能监控工具。可以查看当前应用的对象、对象引用、内存、CPU使用情况、线程、线程运行情况（阻塞、等待等），同时可以查找应用内存使用得热点，即：哪个对象占用的内存比较多；或者CPU热点，即：哪儿方法占用的较大得CPU资源。
<!-- more -->
# 安装版本9.2.1
## 下载地址
官网下载页面  [\[open\]](http://www.ej-technologies.com/download/jprofiler/files)
win64  [\[download\]](http://download-keycdn.ej-technologies.com/jprofiler/jprofiler_windows-x64_9_2_1.exe)
linux  [\[download\]](http://download-keycdn.ej-technologies.com/jprofiler/jprofiler_linux_9_2_1.tar.gz)
## 注册码
> name: any
> company: any
> License key:
> L-Larry_Lau@163.com#23874-hrwpdp1sh1wrn#0620 
> L-Larry_Lau@163.com#36573-fdkscp15axjj6#25257 
> L-Larry_Lau@163.com#5481-ucjn4a16rvd98#6038 
> L-Larry_Lau@163.com#99016-hli5ay1ylizjj#27215 
> L-Larry_Lau@163.com#40775-3wle0g1uin5c1#0674 

## 安装
### linux
```
tar -zxvf jprofiler_linux_9_2_1.tar.gz
mv jprofiler9 /data/install/
cd /data/install/jprofiler9
ln -s jprofiler9 jprofiler
```
### window
1. 填写上面的注册码 
![img](1_reg.png)
2. 创建session
![img](2_create_session.png)
3. 选择远程tomcat版本（6.x）
![img](3_0_remote_tomcat.png)
4. 选择远程机器系统
![img](3_1_remote_machine.png)
5. 选择jvm版本
![img](3_2_remote_jvm.png)
6. 默认jprofiler ui
![img](3_3_start_mode.png)
7. 配置远程机器ip
![img](3_4_remote_addr.png)
8. 配置机器上刚解压的jprofiler路径
![img](3_5_remote_jprofiler.png)
9. 将远程机器上tomcat/bin/startup.sh复制到window上并选择
![img](3_6_gen_remote_tomcat.png)
10. 远程监控端口
![img](3_7_remote_port.png)
11. 复制生成的startup_jprofiler.sh到tomcat/bin/下 通过这个文件运行tomcat, 启动端口监听
12. 结束设置并运行监控
![img](3_8_finish_setting.png)
![img](3_9_start_session.png)
![img](3_10_startup.png)
