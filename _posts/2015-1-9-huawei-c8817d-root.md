---
layout: post
category : Mobile
tagline: "Supporting tagline"
tags : [android,华为,root]
title : 华为荣耀畅玩4 root
---

root的优点不说了，直接上我的步骤。

### 解锁

1. 首先去华为官网申请解锁密码
S/N 和 MEID 在电池后面。

[华为官网unlock](http://www.emui.com/plugin.php?id=unlock)

得到16位的解锁密码，比如1234567812345678

我用了google的adb,fastboot 来unlock


2. 手机进入Bootloader模式(进入Bootloader进入方法：
将手机彻底关机，然后同时按住【电源键】+【音量下键】，
按住10秒左右手机画面显示华为logo不开机时，松开进入到Bootloader模式;
　　注：在关机之前必须进入设置关闭快速启动;

3. 确保你的手机已经正确连接，应该显示手机序列号

	fastboot devices
	
4. 解锁 bootloader
	
	fastboot oem unlock 1234567812345678
	
	注意替换解锁密码呢。

如果没有adb和fastboot.
也有网友的第三方unlock工具，比如

[华为解锁工具下载](http://www.shuajizhijia.com/sjgj/jieshuo/2014/0724/6840.html)

手机在Bootloader模式下，手机连接到电脑，然后打开解锁工具
然后输入解锁码


### root

1. 下载 [华为C8817D第三方中文recovery;](http://pan.baidu.com/s/1mgkgP2g)

2. 然后再工具界面上，输入数字1(刷入第三方中文版recovery)

3. 手机进入recovery模式(华为荣耀畅玩4进入recovery教程：
先将手机彻底关机，在手机关机的状态下，同时按住【电源键】+【音量上键】，
数秒后，待手机震动后松开，即可进入到Recovery模式。

4. recovery模式下，移动选择最后一项【mandfx】，然后选择获取Root权限即可






