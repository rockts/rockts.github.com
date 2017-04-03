---
title: Virtualbox 安装win8 for mac
date: 2015-08-11 23:44:05
categories:
- 技术
tags:
- 运维相关
- 工具使用
---
因为需要在 Win8 上做一些测试，所以需要在 Mac 上装一个 Win8。
因为 Virtualbox 是开源的，所以我选择 Virtualbox。
在用 Virtualbox 安装 Win8 时候报错 `0x000000c4`
网上好多解决方法，都是 win 系统下。win 和 mac 的大体解决思路一样，只是命令有所差别。

### Win 命令
（1）命令行下， 运行下面代码，找到VM名称。

  `"c:\Program Files\Oracle\VirtualBox\VBoxManage.exe"  list vms`

（2）然后在命令行下运行下面的代码，记得先将[vmname]替换为VM名称：

  `"c:\Program Files\Oracle\VirtualBox\VBoxManage.exe" setextradata [vmname] VBoxInternal/CPUM/CMPXCHG16B 1`

### Mac 命令
（1）打开 Mac 自带终端，输入下面命令，找到VM名称。

  `vboxmanage list vms`

（2）然后在命令行下运行下面的代码，记得先将[vmname]替换为VM名称：

  `VBoxManage setextradata "win8" VBoxInternal/CPUM/CMPXCHG16B 1`
>win8 就是我的 vmname

这样就可以正常安装 Win8 了
