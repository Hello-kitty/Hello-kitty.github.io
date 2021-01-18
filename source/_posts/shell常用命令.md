---
title: shell常用命令
date: 2018-11-21 09:21:15
author: green
img: https://i.loli.net/2021/01/18/V6QqDrYAERCv4Sb.png
top: false
cover: false
coverImg: 
password: 
toc: false
mathjax: false
summary: 
categories: 
tags: [linux,shell]
---

## 输出日志

```shell
function log
{
    echo -e "["`date +'%Y-%m-%d %H:%M:%S'`"]:" "<span style=\"color:green\">$*</span>"
}
```