---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [Centos 7,systemctl,Services]
---

## Centos 7 启动服务发生变化

### 系统服务建立

CentOS 7继承了RHEL 7的新的特性，例如强大的systemctl，
而systemctl的使用也使得以往系统服务的/etc/init.d的启动脚本的方式就此改变，

CentOS 7的服务systemctl脚本存放在：/usr/lib/systemd/，有系统（system）和用户（user）之分

在/usr/lib/systemd/system目录下
建立 shadowsocks.services 文件

内容为
	
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

**Systemd targets are represented by target units. Target units end with the .target file extension and their only purpose is to group together other systemd units through a chain of dependencies.**

* 查看现在的Target

		systemctl list-units --type target
		
* 查看所有的Target

		systemctl list-units --type target --all
		
* Changing the Default Target
		
		systemctl set-default name.target
		
* Changing the Current Target

		systemctl isolate name.target
		
* Changing to Rescue Mode

		systemctl rescue
		
This command is similar to systemctl isolate rescue.target

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






