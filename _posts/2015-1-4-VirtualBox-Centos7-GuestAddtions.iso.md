---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [VirtualBox,Centos 7,GuestAddtions]
title : VirtualBox 安装 Centos 7 和GutestAddtions 要点
---

GuestAddtions里面有VirtualBox与Centos的集成，可以共享剪贴板，鼠标可以直接移进移出虚拟机。

直接安装会出错，无法安装上GuestAddtions

### 安装要点记录

1. 内存要大于512MB，才会出现图像安装界面
2. 选Gnome，这样光驱能方便地加载上
3. 安装必要工具

		yum install kernel-devel
		yum install gcc*
		yum install epel-release
		yum install dkms
	
4. devices -> insert guest addional cd image. -> run






