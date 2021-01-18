---
title: win10安装以及配置各种环境
date: 2018-06-10 11:58:11
author: green
img: https://i.loli.net/2021/01/18/sn4oaB8EK6jOkID.jpg
top: false
cover: false
coverImg: 
password: 
toc: false
mathjax: false
summary: 
categories: 
tags: [win10,env]
---
## 使用winPE+EasyBCD引导启动，安装系统
- 去[msdn.itellyou.cn](http://msdn.itellyou.cn)下载win10镜像
- 使用EasyBCD添加启动项
- 用U盘进入winPE从硬盘加载镜像进行安装

## 配置win10各种设置和激活
- 删除已创建账户，启用Administration账户
- 关闭自动更新，包括服务services.smc，组策略gpedit.msc
- 使用kms激活系统

## 安装基础软件
- 解压 [BandZip](http://www.bandisoft.com/bandizip/)
- 剪切板增强 [CLCL](https://www.nakka.com/soft/clcl/)
- 风扇控制 Clevo ECView

## 配置开发环境 
- 安装npm,git,TortoiseGit,Anaconda