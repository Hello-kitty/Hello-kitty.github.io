---
title: shell常用命令
date: 2018-11-21 09:21:15
tags: [linux,shell]
---

## 输出日志

```bash
function log
{
    echo -e "["`date +'%Y-%m-%d %H:%M:%S'`"]:" "<span style=\"color:green\">$*</span>"
}
```