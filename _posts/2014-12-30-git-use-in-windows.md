---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [git,windows,github]
title : git 使用
---

记录一下windows下使用git的要点，含github，git 命令都是运行在git代码的根目录

相比cvs, svn, Git最大的变化是分布式，就是所有的电脑都是SCM服务器，
所谓的上传服务器只是大家都约定好，上传到同一个地方而已。

### git 下载
从这里下载 <http://git-scm.com/downloads>

### git 配置
生成ssh key  
ssh key 使得通过ssh协议来与git服务器交互，这需要服务器的git用户下.ssh目录的authorized_keys文件有你的public key

	$ ssh-keygen -t rsa -C "your_email@example.com"
	
~/.ssh 目录下会生成id_rsa,id_rsa.pub文件
id_rsa.pub 是public key.
把你的ssh public key添加到github上，这样就能上传下载github上的repository了。

    setting -> ssh keys -> Add SSH key
  
设置用户与email和其他设置

    $ git config --global user.name "yourname"
    $ git config --global user.email "your_email@example.com"
    $ git config --global push.default matching

设置代理天朝的网络速度大家都懂的。
本地设置了shadowsocks代理

    $git config --global http.proxy 'socks5://127.0.0.1:8443'
    
### 开始工作

从服务器下载源代码
    $git clone git@github.com:yourname/yourproject.git
	
修改后，提交前，查看所有的变化
	
	$git status

看自己改了什么

	$git diff
    
开始提交，有新增/删除文件的提交方法

    $git add -A  
    $git commit -m "what modified in this time"
	
没有新增文件的提交方法
	
	$git commit -am "what modified in this time"
	
提交到远程

    $git push origin
	
不想提交，清除当前目录所有变化

	$git git checkout -- .

不想提交，清除当前文件A.txt的变化

	$git git checkout -- a.txt

错误提交，删除版本，注意commit_id可以是整个hash key的前面几位

	$git reset --hard commit_id
	
### git鼓励branch的提交,branch的使用

你可以先提交到本地，这样代码就不会丢失，
你可以决定什么时候提交到一个服务器上。

新建并切换到branch Tieckt1

	$git checkout -b Tieckt1

改完后切换回主分支

	$git checkout master
	
合并Ticket1 branch变化到主分支

	$git merge Tieckt1

查看branch

	$git branch

### git 远程命令

查看远程link到哪里

	$git remote -v 
	
查看远程的branch

	$git branch -v

获取远程的变化并自动合并

	$git pull

**安全起见，应该鼓励使用下面的三个命令代替git pull**

获取远程的变化

	$git fetch
	
查看远程的变化

	$git diff origin/master master
	
决定合并

	$git merge origin/master master
	
提交本地变化到远程

	$git push


	


