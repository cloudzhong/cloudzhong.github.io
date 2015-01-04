---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [VirtualBox,Centos 7,GuestAddtions]
---

## VirtualBox 安装centos 7与GuestAddtions

### 要点记录

1. 内存要大于512MB，才会出现图像安装界面
2. 选Gnome，这样光驱能方便地加载上
3. 安装必要工具

		yum install kernel-devel
		yum install gcc*
		yum install epel-release
		yum install dkms
	
4. devices -> insert guest addional cd image. -> run






