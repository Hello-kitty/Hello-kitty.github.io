---
title: git常用命令-1
author: green
date: 2021-03-10 17:01:13
img:
top:
cover:
coverImg:
password:
toc:
mathjax:
summary:
categories:
tags:
  - git
  - linux
---

## git常用命令

```bash
# 初始化仓库
$ git init

# 查看当前Git配置
$ git config --list

# 配置用户信息
$ git config --global user.name "[name]"
$ git config --global user.email "[email]"

# 修改默认编辑器为vscode
$ git config --global core.editor "code --wait"

# 修改默认diff工具为vscode
# 命令行不成功需要手动去编辑 另外需要在vscode中执行code install
$ git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"

# 添加远程仓库
$ git remote add [shortname] [url]

# 添加本地文件快照到本地暂存区
$ git add [filename1] [filename2]
$ git add .

# 提交暂存区文件到本地仓库
$ git commit -m [message]
$ git commit

# 显示工作区相对暂存区有变更的文件
$ git status 
$ git status -s

# 查看暂存区的文件
$ git ls-files

# 查看工作区相对暂存区的变动
$ git diff

# 查看暂存区相对上一次提交的变动
$ git diff --cached

# 从工作区和暂存区同时删除文件
$ git rm [filename]

# 从暂存区中删除文件 保留工作区的文件
$ git rm --cache [filename]

# 查看版本历史记录
$ git log
$ git log --oneline

# 从暂存区删除提交的快照
$ git restore --staged [filename]

# 列出树对象的内容
$ git ls-tree [tree object]

# 显示某次提交的数据变化
$ git show [commit]

# 显示树对象中某个文件的内容
$ git show [tree object]:[filename]
```
