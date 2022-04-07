---
title: python读写Excel
date: 2018-05-18 15:59:22
updated: 2018-05-18 15:59:22
author: green
type:
description:
keywords:
cover: https://i.loli.net/2021/01/18/aIEnH4jKmrDStoU.png
top_img:
categories: 
tags: [python,xlrd,xlwt]
---

python3 使用xlrd和xlwt读取和写入Excel
更新某个excel表格，进行两项操作，且不覆盖原有的sheet：

1. 在原来的excel表中新增sheet
2. 往原有的excel表中的某张sheet新增内容

具体代码如下

```python
import xlwt
import xlrd
from xlutils.copy import copy

path = 'demo.xls'

#打开需要操作的excel表
wb=xlrd.open_workbook(path)

#复制原有表
newb=copy(wb)

#新增sheet,参数是该sheet的名字，可自定义
wbsheet=newb.add_sheet('sheet_nameZzz')

#向新sheet中写入数据。本代码中的d是某个dataframe
wbsheet.write(0,0,'A')
wbsheet.write(0,1,'B')
wbsheet.write(0,2,'C')
for i in range(10):
    for j in range(3):
        wbsheet.write(i+1,j,'{}-{}'.format(i+1,j))

# 获取原有excel表中sheet名为‘summary’的sheet
sumsheet=newb.get_sheet('Sheet1')

#k表示该sheet的最后一行
rows=len(sumsheet.rows)

#想原有sheet后面新增数据
sumsheet.write(rows,0,'{}-0'.format(rows))
sumsheet.write(rows,1,'{}-1'.format(rows))
sumsheet.write(rows,2,'{}-2'.format(rows))

#保存为原有的excel表路径
newb.save(path)
```
