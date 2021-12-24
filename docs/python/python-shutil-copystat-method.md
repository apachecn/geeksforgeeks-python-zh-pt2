# Python | shutil.copystat()方法

> 原文:[https://www . geesforgeks . org/python-shutil-copy stat-method/](https://www.geeksforgeeks.org/python-shutil-copystat-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。Python 中的
***shutil . copy stat()***方法用于将*权限位*、*上次访问时间*、*上次修改时间*、*标志*值从给定的源路径复制到给定的目的路径。
***shutil . copy stat()***方法不影响文件内容和所有者及组信息。
在 Linux 上，除了*权限位*、*上次访问时间*、*上次修改时间*、*标志*值外，该方法还尝试复制一些扩展属性。

> ***语法:*** shutil.copystat(源、目的地、* follow _ symlinks = True)
> ***参数:***
> **源**:代表源文件路径的字符串。
> **目的地**:表示目的文件路径的字符串。
> **follow _ symlink**(可选) :该参数默认值为 True。如果为 False，并且源和目标都引用符号链接，那么 shutil.copystat()方法将对符号链接本身而不是符号链接引用的文件进行操作。
> **注意:**参数列表中的“*”表示以下所有参数(在我们这里是“follow _ symlinks”)都是仅包含关键字的参数，可以使用它们的名称来提供，而不是作为位置参数。
> ***返回类型:*** 此方法不返回任何值。

**代码:**使用 shutil.copystat()方法将元数据从源路径复制到目标路径

## 蟒蛇 3

```py
# Python program to explain shutil.copystat() method

# importing os module
import os

# importing shutil module
import shutil

# importing time module
import time

# Source file path
src = "/home/ihritik/Desktop/sam3.pl"

# Destination file path
dest = "/home/ihritik/Desktop/encry.py"

# Print the permission bits
# last access time, last modification time
# and flags value of source and destination files
print("Before using shutil.copystat() method:")
print("Source metadata:")
print("Permission bits:", oct(os.stat(src).st_mode)[-3:])
print("Last access time:", time.ctime(os.stat(src).st_atime))
print("Last modification time:", time.ctime(os.stat(src).st_mtime))
# print("User defined Flags:", os.stat(src).st_flags)

# Note: st_flags attribute is platform dependent
# and is subject to availability

print("\nDestination metadata:")
print("Permission bits:", oct(os.stat(dest).st_mode)[-3:])
print("Last access time:", time.ctime(os.stat(dest).st_atime))
print("Last modification time:", time.ctime(os.stat(dest).st_mtime))
# print("User defined Flags:", os.stat(dest).st_flags)

# Copy the permission bits
# last access time, last modification time
# and flags value from source to destination
shutil.copystat(src, dest)

# Print the permission bits
# last access time, last modification time
# and flags value of destination
print("\nAfter using shutil.copystat() method:")
print("Destination metadata:")
print("Permission bits:", oct(os.stat(dest).st_mode)[-3:])
print("Last access time:", time.ctime(os.stat(dest).st_atime))
print("Last modification time:", time.ctime(os.stat(dest).st_mtime))
# print("User defined Flags:", os.stat(dest).st_flags)

print("Permission bits, last access time and last modification time\n\
copied from source to destination successfully")
```

**Output:** 

```py
Before using shutil.copystat() method:
Source metadata:
Permission bits: 664
Last access time: Mon Jun 10 00:37:16 2019
Last modification time: Thu Dec 27 00:15:23 2018

Destination metadata:
Permission bits: 777
Last access time: Fri Apr 12 01:13:25 2019
Last modification time: Thu Apr 11 02:03:45 2019

After using shutil.copystat() method:
Destination metadata:
Permission bits: 664
Last access time: Mon Jun 10 00:37:16 2019
Last modification time: Thu Dec 27 00:15:23 2018

Permission bits, last access time and last modification time
copied from source to destination successfully
```

**参考:**T2https://docs.python.org/3/library/shutil.html