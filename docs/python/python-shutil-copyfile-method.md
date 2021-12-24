# Python | shutil.copyfile()方法

> 原文:[https://www . geesforgeks . org/python-shutil-copy file-method/](https://www.geeksforgeeks.org/python-shutil-copyfile-method/)

## 蟒蛇 3

```py
# Python program to explain shutil.copyfile() method

# importing shutil module
import shutil

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents"

# Copy the content of
# source to destination

try:
    shutil.copyfile(source, destination)
    print("File copied successfully.")

# If source and destination are same
except shutil.SameFileError:
    print("Source and destination represents the same file.")

# If destination is a directory.
except IsADirectoryError:
    print("Destination is a directory.")

# If there is any permission issue
except PermissionError:
    print("Permission denied.")

# For other errors
except:
    print("Error occurred while copying file.")
```

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
***shutil . copy file()***Python 中的方法是将*源文件的内容复制到*目标*文件中。不复制文件的元数据。*源*和*目的地*必须代表一个文件，*目的地*必须是可写的。如果*目标*已经存在，那么它将被*源*文件替换，否则将创建一个新文件。
如果*源*和*目的地*代表同一个文件，则*相同文件错误*异常将被引发。* 

> ***语法:*** shutil.copyfile(源、目的地、* follow _ symlinks = True)
> ***参数:***
> **source** :代表源文件路径的字符串。
> **目的地**:表示目的文件路径的字符串。
> **follow _ symlink**(可选) :该参数默认值为 True。如果“假”和“源”表示符号链接，则将创建一个新的符号链接，而不是复制文件。
> **注意:**参数列表中的“*”表示以下所有参数(在我们这里是“follow _ symlinks”)都是仅包含关键字的参数，可以使用它们的名称来提供，而不是作为位置参数。
> ***返回类型:*** 该方法返回一个代表新创建文件路径的字符串。

**代码#1:** 使用 shutil.copyfile()方法将文件从源复制到目标

## 蟒蛇 3

```py
# Python program to explain shutil.copyfile() method

# importing os module
import os

# importing shutil module
import shutil

# path
path = '/home/User/Documents'

# List files and directories
# in '/home/User/Documents'
print("Before copying file:")
print(os.listdir(path))

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents/file(copy).txt"

# Copy the content of
# source to destination
dest = shutil.copyfile(source, destination)

# List files and directories
# in "/home / User / Documents"
print("After copying file:")
print(os.listdir(path))

# Print path of newly
# created file
print("Destination path:", dest)
```

**Output:** 

```py
Before copying file:
['hrithik.png', 'test.py', 'sample.txt', 'file.text', 'copy.cpp']
After copying file:
['hrithik.png', 'test.py', 'sample.txt', 'file.text', 'file(copy).txt', 'copy.cpp']
Destination path: /home/User/Documents/file(copy).txt
```

**代码#2:** 使用 shutil.copyfile()方法时可能出现的错误

## 蟒蛇 3

```py
# Python program to explain shutil.copyfile() method

# importing shutil module
import shutil

# If the source and destination
# represents the same file
# 'SameFileError' exception
# will be raised

# If the destination is
# is directory then
# 'IsADirectoryError' exception
# will be raised

# If the destination is
# not writable
# 'PermissionError' exception
# will be raised

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents/file.txt"

# Copy the content of
# source to destination
shutil.copyfile(source, destination)
```

**Output:** 

```py
Traceback (most recent call last):
  File "copy.py", line 31, in 
    shutil.copyfile(source, destination)
  File "/usr/lib/python3.6/shutil.py", line 104, in copyfile
    raise SameFileError("{!r} and {!r} are the same file".format(src, dst))
shutil.SameFileError: '/home/User/Documents/file.txt' and '/home/User/Documents/file.txt'
are the same file
```

**代码#3:** 使用 shutil.copyfile()方法时处理错误

## 蟒蛇 3

```py
# Python program to explain shutil.copyfile() method

# importing shutil module
import shutil

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents"

# Copy the content of
# source to destination

try:
    shutil.copyfile(source, destination)
    print("File copied successfully.")

# If source and destination are same
except shutil.SameFileError:
    print("Source and destination represents the same file.")

# If destination is a directory.
except IsADirectoryError:
    print("Destination is a directory.")

# If there is any permission issue
except PermissionError:
    print("Permission denied.")

# For other errors
except:
    print("Error occurred while copying file.")
```

**Output:** 

```py
Destination is a directory.
```

**参考:**T2https://docs.python.org/3/library/shutil.html