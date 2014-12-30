---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [git,windows,github]
---

记录一下windows下使用git, github的要点
======================================

### git 下载
从这里下载 http://git-scm.com/downloads

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

    $git clone git@github.com:yourname/yourproject.git
    
开始提交

    $git add -A  
    $git commit -m "what modified in this time"
	
提交到github

    $git push origin




