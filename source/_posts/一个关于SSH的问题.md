---
title: 一个关于SSH的问题
date: 2015-07-28 23:35:35
categories:
- 技术
tags:
- 运维相关
---
mac 不能 ssh  服务器 ，报错提示

`Received disconnect from 123.57.13.0: 2: Too many authentication failures for root`

换了命令行工具依然出错，用其他电脑连接一切正常。
以前服务器绑定过 mac 的ssh-key.pub，因为 mac 上的 ssh-key 变更过。
所以导致服务器验证通不过。查了相关资料后。
再 ssh 后面 加上

`-o PubkeyAuthentication=no`

这个参数，连接正常。

最后登录服务修改

`/etc/ssh/sshd_config` 文件

`MaxAuthTries=2`

参数等于2,一些正常，重新绑定 mac ssh-key.pub
