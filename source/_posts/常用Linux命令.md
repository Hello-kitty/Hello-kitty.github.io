---
title: 常用Linux命令
date: 2018-09-10 10:27:11
author: green
img: 
top: true
cover: false
coverImg: 
password: 
toc: false
mathjax: false
summary: 
categories: 
tags: [linux]
---

## grep
```bash
Usage: grep [OPTION]... PATTERN [FILE]...

    -R, -r, --recursive       递归 equivalent to --directories=recurse
      --include=FILE_PATTERN  匹配文件名包含 search only files that match FILE_PATTERN
      #只在目录中所有的.php和.html文件中递归搜索字符 grep -r "xxx" ./ --include *.{php,html} 
      --exclude=FILE_PATTERN  跳过文件名包含 skip files and directories matching FILE_PATTERN
      --exclude-from=FILE   跳过指定文件 skip files matching any file pattern from FILE
      --exclude-dir=PATTERN  跳过文件夹名包含 directories that match PATTERN will be skipped.
    -v, --invert-match        反匹配,列出未匹配的 select non-matching lines
    -n, --line-number         列出匹配的的内容的行号 print line number with output lines
    -l, --files-with-matches  列出匹配到内容的文件名称 print only names of FILEs containing matches

```

## netstat
```bash
usage: netstat [-vWeenNcCF] [<Af>] -r         netstat {-V|--version|-h|--help}
       netstat [-vWnNcaeol] [<Socket> ...]
       netstat { [-vWeenNac] -I[<Iface>] | [-veenNac] -i | [-cnNe] -M | -s [-6tuw] } [delay]

netstat -anp
    -n, --numeric            don't resolve names
    -p, --programs           display PID/Program name for sockets
    -a, --all                display all sockets (default: connected)

```

## ps
```bash
ps -ef 

```

## awk

```bash
cat  access_log | grep "14/Dec/2015:19:47" | awk -F " " '{if($15>0.00001) print $15}'  | wc -l
cat access.log | grep "08/Nov/2018:16" | awk -F " " '{if ($25>0.538) print $25}' | wc -l

ps -ef | grep zookeeper | grep -v grep | awk '{print $2}' | xargs kill -9

test.txt

Marry 2143 78 84 77
Jack 2321 66 78 45
Tom 2122 48 77 71
Mike 2537 87 97 95
Bob 2415 40 57 62

awk 'BEGIN{math=0;eng=0;com=0;printf "Lineno.   Name    No.    Math   English   Computer    Total\n";printf "------------------------------------------------------------\n"}{math+=$3; eng+=$4; com+=$5;printf "%-8s %-7s %-7s %-7s %-9s %-10s %-7s \n",NR,$1,$2,$3,$4,$5,$3+$4+$5} END{printf "------------------------------------------------------------\n";printf "%-24s %-7s %-9s %-20s \n","Total:",math,eng,com;printf "%-24s %-7s %-9s %-20s \n","Avg:",math/NR,eng/NR,com/NR}' test.txt

```
![输出结果](https://i.loli.net/2018/11/21/5bf4b84fe622a.jpg)

## sed
```bash
sed [-nefr] [动作]
选项与参数：
-n ：使用安静(silent)模式。在一般 sed 的用法中，所有来自 STDIN 的数据一般都会被列出到终端上。但如果加上 -n 参数后，则只有经过sed 特殊处理的那一行(或者动作)才会被列出来。
-e ：直接在命令列模式上进行 sed 的动作编辑；
-f ：直接将 sed 的动作写在一个文件内， -f filename 则可以运行 filename 内的 sed 动作；
-r ：sed 的动作支持的是延伸型正规表示法的语法。(默认是基础正规表示法语法)
-i ：直接修改读取的文件内容，而不是输出到终端。

动作说明： [n1[,n2]]function
n1, n2 ：不见得会存在，一般代表『选择进行动作的行数』，举例来说，如果我的动作是需要在 10 到 20 行之间进行的，则『 10,20[动作行为] 』

function：
a ：新增， a 的后面可以接字串，而这些字串会在新的一行出现(目前的下一行)～
c ：取代， c 的后面可以接字串，这些字串可以取代 n1,n2 之间的行！
d ：删除，因为是删除啊，所以 d 后面通常不接任何咚咚；
i ：插入， i 的后面可以接字串，而这些字串会在新的一行出现(目前的上一行)；
p ：列印，亦即将某个选择的数据印出。通常 p 会与参数 sed -n 一起运行～
s ：取代，可以直接进行取代的工作哩！通常这个 s 的动作可以搭配正规表示法！例如 1,20s/old/new/g 就是啦！
```