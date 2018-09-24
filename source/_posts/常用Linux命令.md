---
title: 常用Linux命令
date: 2018-09-10 10:27:11
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