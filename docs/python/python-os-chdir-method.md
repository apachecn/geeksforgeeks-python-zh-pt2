# Python os.chdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-chdir-method/](https://www.geeksforgeeks.org/python-os-chdir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统，属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
**Python 中的 os.chdir()** 方法用于将当前工作目录更改为指定路径。它只接受一个参数作为新的目录路径。

> **语法:** os.chdir(路径)
> **参数:**
> **路径:**要更改为新目录路径的目录的完整路径。
> **返回:**不返回任何值

**代码#1:** 使用 chdir()更改目录

## 蟒蛇 3

```py
# Python3 program to change the
# directory of file using os.chdir() method

# import os library
import os

# change the current directory
# to specified directory
os.chdir(r"C:\Users\Gfg\Desktop\geeks")

print("Directory changed")
```

**输出:**

```py
Directory changed
```

**代码#2:** 使用 os.getcwd()
要知道文件的当前工作目录，可以使用 getcwd()方法。更改路径后，可以使用此方法验证当前工作目录的路径。

## 蟒蛇 3

```py
# import os module
import os

# change the current working directory
# to specified path
os.chdir('c:\\gfg_dir')

# verify the path using getcwd()
cwd = os.getcwd()

# print the current directory
print("Current working directory is:", cwd)
```

**输出:**

```py
Current working directory is: c:\\gfg_dir
```

**代码#3:** 更改目录时处理错误

## 蟒蛇 3

```py
# importing all necessary libraries
import sys, os

# initial directory
cwd = os.getcwd()

# some non existing directory
fd = 'false_dir / temp'

# trying to insert to false directory
try:
    os.chdir(fd)
    print("Inserting inside-", os.getcwd())

# Caching the exception   
except:
    print("Something wrong with specified\
          directory. Exception- ", sys.exc_info())

# handling with finally         
finally:
    print("Restoring the path")
    os.chdir(cwd)
    print("Current directory is-", os.getcwd())
```

**输出:**

```py
Inserting inside- c:\gfg_dir\gfg
Something wrong with specified directory. Exception- 
Restoring the path
Current directory is- c:\gfg_dir\gfg
```