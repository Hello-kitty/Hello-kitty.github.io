---
title: sublime Text配置
date: 2021-10-09 17:29:32
updated: 2021-10-09 17:29:32
author: green
type:
description:
keywords:
cover:
top_img:
categories:
tags:
  - sublime Text
  - 编辑器
---

## sublime Text 配置

- 基础配置

```json
{
  "font_size": 15,
  "tab_size": 4, //一次缩进4个空格
  "word_wrap": true, //自动换行
  "indent_using_spaces": true, //使用空格缩进
  "draw_white_space": "all", //显示所有空白字符
  "translate_tabs_to_spaces": true, //tab自动转化为空格
  "trim_trailing_white_space_on_save": true, //保存时去除尾部多余空格
  "expand_tabs_on_save": true, //保存时重写tab设置
  "shift_tab_unindent": true, //使 shift+tab 等效为 command+{快捷键
  "ensure_newline_at_eof_on_save": true, //确保文件结尾有一个空行
  "spell_check": true, //开启拼写检查
  "line_numbers": true, //显示行号
  "folder_exclude_patterns": [".svn", ".git", ".hg", "CVS", "node_modules"] //忽略查找元素
  // "ignored_packages": ["Vintage"],   //忽略使用的插件
  // "color_scheme": "Packages/Color Scheme - Default/Monokai.tmTheme",   //颜色风格
  // "save_on_focus_lost": true,        //失去焦点时储存
  // "atmic_save": true                 //自动存储
}
```

- 配置保存文件时 tab 自动转换为空格

1. Preference -> Browser Packages
2. 新建文件夹 ExpandTabsOnSave
3. 新建文件 ExpandTabsOnSave.py
4. python 文件内容如下

```python
import sublime, sublime_plugin, os

class ExpandTabsOnSave(sublime_plugin.EventListener):
    def on_pre_save(self, view):
        if view.settings().get('expand_tabs_on_save') == 1:
            view.window().run_command('expand_tabs')
```
