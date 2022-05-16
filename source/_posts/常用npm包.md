---
title: 常用npm包
author: green
date: 2022-05-16 17:34:22
updated: 2022-05-16 17:34:22
type:
description:
keywords:
cover: https://i.loli.net/2021/01/18/WEknwdG1eRolrIj.png
top_img:
categories:
tags: [npm, linux]
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

## npm-check-updates

```bash
Usage: ncu -<command>

Commands:
  u [packagename]     升级包
```

>查看node和npm版本对应关系 <https://nodejs.org/zh-cn/download/releases/>
