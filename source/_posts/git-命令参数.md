---
title: git 命令参数
categories:
  - 技术
tags:
  - Git命令
  - 开发参考
date: 2016-05-02 03:18:32
---
# `git clone <远程git仓库地址>`
克隆远程项目
## `git clone -b <远程分支名> <远程git仓库地址>`
克隆远程分支名

# `git branch`   
列出本地已经存在的分支
## `git branch -r`
列出远程分支
## `git branch -a`
列出本地分支和远程分支
## `git branch <分支名>`
创建新的分支
## `git branch -m <旧分支名> <新分支名>`
重命名分支
## `git branch -d <分支名>`
删除分支
## `git branch -d -r <分支名>`
删除远程分支
## `git branch -v`
显示分支最后提交

# `git checkout`
切换分支
## `git checkout <分支名>`
切换具体分支
## `git checkout -b <分支名>`
新建分支切换该分支
### `git checkout -b <分支名a> <远程名>/<分支名a>`
本地新建分支a 与远程名/分支a 对应
## `git checkout -t <远程名>/<分支a>`
默认本地建立一个和远程分支a 一样的分支a

# `git merge <分支名>`
合并分支到当前分支中
