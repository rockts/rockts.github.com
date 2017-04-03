---
title: Vagrant的问题的汇总（不定时更新）
categories:
  - 技术
tags:
  - 运维相关
  - Vagrant
  - 虚拟机
date: 2016-04-29 05:19:04
---
# 启动问题
## 关于 default: Warning: Authentication failure. Retrying...
### 现象
 再用 `vagrant up` 启动虚拟机 或者 `vagrant reload` 重启虚拟机的时候  
 一直不停的报错 default: Warning: Authentication failure. Retrying...
### 解决
在 Vagrantfile 这个文件里面添加了这两行，然后关掉关掉虚拟机。  
`config.ssh.username = "vagrant"`  
`config.ssh.password = "vagrant"`  
注释掉这两行代码  
`vagrant reload`  重启虚拟机，问题解决。
