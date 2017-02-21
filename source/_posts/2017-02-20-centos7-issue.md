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
系统日志不停打印，是因为系统在尝试加载软驱，而它不存在，关掉即可
```
echo "blacklist floppy" | sudo tee /etc/modprobe.d/nofloppy.conf
reboot
```
---
<!-- more -->
