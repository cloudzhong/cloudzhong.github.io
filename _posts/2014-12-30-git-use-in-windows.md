---
layout: post
category : Learn
tagline: "Supporting tagline"
tags : [git,windows,github]
---

## 如何使用git, github

### git download
from http://git-scm.com/downloads

### git config
generate ssh key 
    $ ssh-keygen -t rsa -C "your_email@example.com"
add your key to github
  setting -> ssh keys -> Add SSH key
set your name and email	
    $ git config --global user.name "yourname" 
    $ git config --global user.email "your_email@example.com"
set proxy 天朝的网络速度大家都懂的。
    $git config --global http.proxy 'socks5://127.0.0.1:8443'
开始工作
	$git clone git@github.com:yourname/yourproject.git
开始提交
    $git add -A
	$git commit -m "what modified in this time"
提交到github	
	$git push origin

	
	


