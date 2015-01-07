---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [Centos 7,systemctl,Services]
Title : Centos 7 启动level自定义
---

systemctl单元有很多，最重要的应该是service和target，
service都是服务，
target是一些服务和其他单元的集合。
target使得自定义runlevel变得轻松和易读。


### 自定义服务建立

systemctl的使用也使得以往系统服务的/etc/init.d的启动脚本的方式就此改变，
自定义服务的方式如下

在/usr/lib/systemd/system目录下
建立 shadowsocks.services 文件

内容为
	
	[Unit]
	Description=shadowsocks server
	After=network.target remote-fs.target nss-lookup.target

	[Service]
	ExecStart=/usr/bin/ssserver -c /etc/shadowsocks.json
	KillMode=process

	[Install]
	WantedBy=multi-user.target
	

开始服务

	systemctl enable shadowsocks.service
	systemctl start shadowsocks.service

		
修改services文件后，需要重新加载

	systemctl daemon-reload
	

### systemctl 用法

* 显示服务状态
		
		systemctl status name.service

* 重启服务
		
		systemctl restart name.service
	
* 不中断服务，重新加载配置

		systemctl reload name.service
	
* 成为服务

		systemctl enable name.service

* 启动服务

		systemctl start name.service
		
* 禁止服务

		systemctl disable name.service
		
### SYSTEMD TARGETS

**Target只有一个作用，集合所有的SystemD的单元，并且管理他们的依赖。**

centos 7 之前只能用init 3, init 5 之类的来指定运行级别，
Centos 7 可以自定义指定的级别来启动，可以包含自己想启动的服务，可以去掉默认的服务。
因为service都是包含在指定的target里面的。

* 查看现在系统运行的Target

		systemctl get-default

* 查看现在加载的Target

		systemctl list-units --type target
		
* 查看所有的Target

		systemctl list-units --type target --all
		
* 设置默认的 Target
		
		systemctl set-default name.target
		
		
* 改变当前的 Target

		systemctl isolate name.target
		
* 切换到急救模式

		systemctl rescue
		
这个命令和`systemctl isolate rescue.target` 一样的

### 关机 挂起 休眠 系统

* 关机

		systemctl poweroff
		
* halt

		systemctl halt
		
* 重启

		systemctl reboot
		
* 挂起

		systemctl suspend
		
* 休眠系统

		systemctl hibernate






