---
title: 关于天水跳蚤session的问题
categories:
  - 技术
tags:
  - 运维备忘
  - 问题解决
date: 2016-05-11 23:37:07
---
>*问题反反复复的出了2，3次，今天记录下解决办法。怕日后忘记*

# 问题表现

* 登录后台输入验证码，老提示输入错误
* 前台登录后不显示用户登录信息   

# 解决办法
* 登录服务器查看 php-fpm 配置文件
* 查找 session.save_path 目录
* 进入 session 存储目录，查看该目录所有者
* 修复该目录所有者为当前 php 服务执行者

# 具体过程
`cd /etc/php-fpm.d/` *进入 php-fpm 目录*  
`vi www.conf` *查找 php_value[session.save_path] 目录*  
`cd /var/lib/php-fpm/`  *进入 php_value[session] 存储目录*  
`ls -la`  *查看 session 目录所有者*  
`su root` *切换 root 账号*  
`chown -R leke:leke session`  *设置 session 目录所有者为 leke 组 leke 用户*   
> 因为之前我修改过 php nginx php-fpm 默认用户   
> 所以要把 session 目录所有者改成我设置的用户  
> php 才有权限执行 session 会话
