# Python | os.lchflags()方法

> 原文:[https://www.geeksforgeeks.org/python-os-lchflags-method/](https://www.geeksforgeeks.org/python-os-lchflags-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**`os.lchflags()`** 方法在 Python 中用于将指定路径的标志设置为数字标志，
该方法类似于 [**`os.chflags()`**](https://www.geeksforgeeks.org/python-os-chflags-method/) 方法，但它不遵循符号链接。

**注意:**此方法仅在 Unix 平台上可用。

> **语法:**OS . lcflag(路径、标志)
> 
> **参数:**
> **路径:**表示有效系统路径的类路径对象。它可以是表示路径的字符串对象或字节对象。
> **标志:**表示路径标志的数值，或者是 stat 模块中定义的以下值的组合(按位或)
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
> **返回类型:**该方法不返回值。

**代码:**使用 **`os.lchflags()`** 方法

```py
# Python3 program to explain os.lchflags() method

# importing os library
import os

# Path
path = "GeeksForGeeks/sample.txt"

# Flag value
flag = os.UF_NODUMP

# Change the flag of the
# specified path using
# os.lchflags() method
os.lchflags(path, flag)

print("Flag changed successfully")
```

**Output:**

```py
Flag changed successfully

```