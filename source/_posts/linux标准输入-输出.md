---
title: linux标准输入&输出
date: 2018-11-07 15:23:53
author: green
img: https://i.loli.net/2021/01/18/sWBpIr5jSNMlk97.png
top: false
cover: false
coverImg: 
password: 
toc: false
mathjax: false
summary: 
categories: 
tags: [linux]
---

## Linux标准输入输出

- 标准输入0    从键盘获得输入 /proc/self/fd/0 
- 标准输出1    输出到屏幕（即控制台） /proc/self/fd/1 
- 错误输出2    输出到屏幕（即控制台） /proc/self/fd/2 

```
/dev/null代表linux的空设备文件，所有往这个文件里面写入的内容都会丢失，俗称“黑洞” 
- 2>/dev/null意思就是把错误输出到“黑洞” 
- >/dev/null 2>&1默认情况是1，也就是等同于1>/dev/null 2>&1。意思就是把标准输出重定向到“黑洞”，还把错误输出2重定向到标准输出1，也就是标准输出和错误输出都进了“黑洞” 
- 2>&1 >/dev/null意思就是把错误输出2重定向到标准出书1，也就是屏幕，标准输出进了“黑洞”，也就是标准输出进了黑洞，错误输出打印到屏幕 
关于这里”&”的作用，我们可以这么理解2>/dev/null重定向到文件，那么2>&1，这里如果去掉了&就是把错误输出给了文件1了，用了&是表明1是标准输出。
```