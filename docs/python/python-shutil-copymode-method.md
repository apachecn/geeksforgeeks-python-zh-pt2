# Python | shutil.copymode()方法

> 原文:[https://www . geesforgeks . org/python-shutil-copy mode-method/](https://www.geeksforgeeks.org/python-shutil-copymode-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动化文件和目录的复制和删除过程。
***Python 中的 shutil.copymode()*** 方法用于将*权限位*从给定的源路径复制到给定的目标路径。
***shutil . copy mode()***方法不影响文件内容或所有者和组信息。

> ***语法:*** shutil.copymode(源、目的地、* follow _ symlinks = True)
> ***参数:***
> **源**:代表源文件路径的字符串。
> **目的地**:表示目的文件路径的字符串。
> **follow _ symlink**(可选) :该参数默认值为 True。如果为 False，并且源和目标都引用了符号链接，那么 shutil.copymode()方法将尝试修改目标(这是一个符号链接)本身的模式，而不是它所指向的文件。
> **注意:**参数列表中的“*”表示以下所有参数(在我们这里是“follow _ symlinks”)都是仅包含关键字的参数，可以使用它们的名称来提供，而不是作为位置参数。
> ***返回类型:*** 此方法不返回任何值。

**代码:**使用 shutil.copymode()方法将许可位从源路径复制到目的路径

## 蟒蛇 3

```
# Python program to explain shutil.copymode() method

# importing os module
import os

# importing shutil module
import shutil

# Source file path
src = "/home/ihritik/Desktop/sam3.pl"

# Destination file path
dest = "/home/ihritik/Desktop/encry.py"

# Print the permission bits
# of source and destination path

# As we know, st_mode attribute
# of ‘stat_result’ object returned
# by os.stat() method is an integer
# which represents file type and
# file mode bits (permissions)
# So, here integere is converted into octal form
# to get typical octal permissions.
# Last 3 digit represents the permission bits
# and rest digits represents the file type
print("Before using shutil.copymode() method:")
print("Permission bits of source:", oct(os.stat(src).st_mode)[-3:])
print("Permission bits of destination:", oct(os.stat(dest).st_mode)[-3:])

# Copy the permission bits
# from source to destination
shutil.copymode(src, dest)

# Print the permission bits
# of destination path
print("\nAfter using shutil.copymode() method:")
print("Permission bits of destination:", oct(os.stat(dest).st_mode)[-3:])
```

**Output:** 

```
Before using shutil.copymode() method:
Permission bits of source: 664
Permission bits of destination: 777

After using shutil.copymode() method:
Permission bits of destination: 664
```

**参考:**T2https://docs.python.org/3/library/shutil.html