---
title: python参数
date: 2021-01-29 21:41:58
updated: 2021-01-29 21:41:58
author: green
type:
description:
keywords:
cover: https://i.loli.net/2021/01/29/eSwRCgsLmQfdznH.png
top_img:
categories:
tags: [python]
---

## python 参数

### 函数的参数

可变参数 (Variable Argument) 的方法：使用*args和**kwargs语法。其中，*args是可变的positional arguments列表，**kwargs是可变的keyword arguments列表。并且，*args必须位于**kwargs之前，因为positional arguments必须位于keyword arguments之前。

```python
def test_args(first, *args, **kwargs):
    print('Required argument is:',first)
    for i in args:
        print('Optional argument (*args) is:', i)
    for j,k in kwargs.items():
        print('Optional argument %s (**kwargs) is: %s' % (j,k))

test_args(99)
test_args('a', k1=9)
test_args(1,5,6,'a','b',k1=6,k2=7)
# output:
# Required argument is: 99
# Required argument is: a
# Optional argument k1 (**kwargs) is: 9
# Required argument is: 1
# Optional argument (*args) is: 5
# Optional argument (*args) is: 6
# Optional argument (*args) is: a
# Optional argument (*args) is: b
# Optional argument k1 (**kwargs) is: 6
# Optional argument k2 (**kwargs) is: 7
```

*args和**kwargs语法不仅可以在函数定义中使用，同样可以在函数调用的时候使用。不同的是，如果说在函数定义的位置使用*args和**kwargs是一个将参数pack的过程，那么在函数调用的时候就是一个将参数unpack的过程了。下面使用一个例子来加深理解：

```python
def test_args(first, second, third, fourth, fifth):
    print ('First argument: ', first)
    print ('Second argument: ', second)
    print ('Third argument: ', third)
    print ('Fourth argument: ', fourth)
    print ('Fifth argument: ', fifth)

# Use *args
args = [1, 2, 3, 4, 5]
test_args(*args)
# results:
# First argument:  1
# Second argument:  2
# Third argument:  3
# Fourth argument:  4
# Fifth argument:  5

# Use **kwargs
kwargs = {
    'first': 1,
    'second': 2,
    'third': 3,
    'fourth': 4,
    'fifth': 5
}

test_args(**kwargs)
# results:
# First argument:  1
# Second argument:  2
# Third argument:  3
# Fourth argument:  4
# Fifth argument:  5
```
