---
title: 常用npm包
date: 2018-09-10 09:32:32
author: green
img: 
top: false
cover: false
coverImg: 
password: 
toc: false
mathjax: false
summary: 
categories: 
tags: [npm]
---

## hexo

```bash
Usage: hexo <command>

Commands:
  clean     清除静态文件 Remove generated files and cache.
  deploy    将pbulic下的今天资源推送到指定仓库上,需要先配置config里的deploy Deploy your website.
  generate  生成静态文件 Generate static files.
  init      项目初始化 Create a new Hexo folder. 
  new       新建一个文章 Create a new post.
  server    开启本地服务 Start the server.
  
  常用的可以简写为:
  hexo g
  hexo s 等..
  
```

## browser-sync
```bash
browser-sync start --server --files "xx"
多个文件用,分隔,例如"index.html,css/*.css"

```