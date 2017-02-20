---
title: centos7-issue
date: 2017-02-20 20:51:04
categories:
	- service
	- centos7
tags:
	- centos7
---
# 系统启动错误
---
## end_request: I/O error, dev fd0, sector 0
```
echo "blacklist floppy" | sudo tee /etc/modprobe.d/nofloppy.conf
reboot
```
---
<!-- more -->
