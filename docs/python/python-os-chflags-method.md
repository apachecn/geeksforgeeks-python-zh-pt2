# Python | os.chflags()方法

> 原文:[https://www.geeksforgeeks.org/python-os-chflags-method/](https://www.geeksforgeeks.org/python-os-chflags-method/)

**[Python 中的 OS 模块](https://www.geeksforgeeks.org/os-path-module-python/)** 提供了与操作系统交互的功能。这属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**`os.chflags()`** 方法在 Python 中用于将路径的标志设置为数字标志；仅在 Unix 中可用。标志可以采用标志值的组合(按位“或”)。

> **语法:** os.chflag(路径，标志)
> 
> **参数:**
> **路径:**一个目录的完整路径要改成新的目录路径。
> **标志:**取下列标志值的组合(按位“或”)
> 
> **os。UF _ NODUMP**–不要转储文件。
> **os。不可变的**–文件不可更改(只读)。
> **os。UF _ APPEND**–文件只能追加到。
> **os。不透明**–目录不透明，通过联合堆栈查看。
> **os。UF _ NOUN link**–文件不得重命名或删除。
> **os。UF _ COMPLATED**–文件以压缩方式存储
> **os。UF _ HIDDEN**–文件不应显示在图形用户界面
> **操作系统中。SF _ ARCHED**–文件可以存档。(超级用户可以设置)
> **os。SF _ INCOVERTY**–文件不得更改。(超级用户可设置)
> **os。SF _ APPEND**–文件只能附加到。(超级用户可设置)
> **os。**文件不能被重命名或删除。(超级用户可以设置)
> **os。SF _ SNAPSHOT**–文件是快照文件。(可以设置超级用户)
> 
> **返回:**不返回值

```
# Python3 program to change directory 
# of file using os.chflags() method

# import os library
import os

# defining path and flag
path = "gfg_dir/geek.txt"
flag = os..UF_IMMUTABLE

# assigning val to function chflags()
val = os.chflags(path, flag)

# Doesn't return any value, so
# nothing will be printed
print("Operation successful, returning value: %s" %val)
```

输出:

```
Operation successful, returning value: None
```