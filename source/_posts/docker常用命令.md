---

title: docker常用命令
date: 2021-01-15 19:35:31
updated: 2022-01-15 19:35:31
author: green
type:
description:
keywords:
cover: https://i.loli.net/2021/01/17/LthCmfp5gdPTHWZ.png
top_img:
categories: Develop Tools
tags: [docker, linux]
---

## docker常用命令

- 显示所有镜像
```bash
docker images
```

- 显示所有容器
```bash 
docker ps
Options:
  -a, --all             Show all containers (default shows just running)
  -q, --quiet           Only display container IDs
```

- 启动容器
```bash
docker run -it  -d [imageid] /bin/bash
```
|选项|选项简写|说明|
|:---|:--:|:---|
|--interactive|-i|即使没有连接，也要保持标准输入保持打开状态，一般与-t连用|
|--tty|-t|分配一个伪tty，一般与-i连用|
|--detach|-d|在后台运行容器，并且打印容器id|


- 启动已停止容器
```bash
docker start [containerid]
```

- 关闭所有正在运行的容器
```bash
docker kill $(docker ps -q)
```

- 进入一个容器
```bash 
docker exec -it [containerid] /bin/bash
或者
docker exec -it [containerid] sh
```