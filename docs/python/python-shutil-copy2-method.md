# Python | shutil.copy2()方法

> 原文:[https://www.geeksforgeeks.org/python-shutil-copy2-method/](https://www.geeksforgeeks.org/python-shutil-copy2-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
***shutil . copy 2()***Python 中的方法用于将*源文件的内容复制到*目标*文件或目录中。此方法与***shutil . copy()***方法相同，但它也尝试保留文件的元数据。
*源*必须代表一个文件，而*目的*可以是一个文件，也可以是一个目录。如果目标是一个目录，那么文件将使用来自源的基本文件名复制到目标中。另外，*目的地*必须可写。如果*目标*是一个文件并且已经存在，那么它将被*源*文件替换，否则将创建一个新文件。* 

> ***语法:*** shutil.copy2(源、目的地、* follow _ symlinks = True)
> ***参数:***
> **源**:代表源文件路径的字符串。
> **目的地**:表示目的文件或目录路径的字符串。
> **follow _ symlink**(可选) :该参数默认值为 True。如果为 False，并且源表示符号链接，则它会尝试将所有元数据从源符号链接复制到新创建的目标符号链接。该功能依赖于平台。
> **注意:**参数列表中的“*”表示以下所有参数(在我们这里是“follow _ symlinks”)都是仅包含关键字的参数，可以使用它们的名称来提供，而不是作为位置参数。
> ***返回类型:*** 该方法返回一个代表新创建文件路径的字符串。

**代码#1:** 使用 shutil.copy2()方法将文件从源复制到目标

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method

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

# Print the metadeta
# of source file
metadata = os.stat(source)
print("Metadata:", metadata, "\n")

# Destination path
destination = "/home/User/Documents/file(copy).txt"

# Copy the content of
# source to destination
dest = shutil.copy2(source, destination)

# List files and directories
# in "/home / User / Documents"
print("After copying file:")
print(os.listdir(path))

# Print the metadata
# of the destination file
matadata = os.stat(destination)
print("Metadata:", metadata)

# Print path of newly
# created file
print("Destination path:", dest)
```

**Output:** 

```py
Before copying file:
['hrithik.png', 'test.py', 'sample.txt', 'file.text', 'copy.cpp']
Metadata:  os.stat_result(st_mode=33188, st_ino=801113, st_dev=2056, st_nlink=1,
st_uid=1000, st_gid=1000, st_size=84, st_atime=1558866178, st_mtime=1558866156, 
st_ctime=1558866156) 

After copying file:
['hrithik.png', 'test.py', 'sample.txt', 'file.text', 'file(copy).txt', 'copy.cpp']
Metadata: os.stat_result(st_mode=33188, st_ino=801111, st_dev=2056, st_nlink=1,
st_uid=1000, st_gid=1000, st_size=84, st_atime=1558866178, st_mtime=1558866156,
st_ctime=1558933947)
Destination path: /home/User/Documents/file(copy).txt
```

**代码#2:** 如果目的地是目录

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method

# importing os module
import os

# importing shutil module
import shutil

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Desktop/"

# Copy the content of
# source to destination
dest = shutil.copy2(source, destination)

# List files and directories
# in "/home / User / Desktop"
print("After copying file:")
print(os.listdir(destination))

# Print path of newly
# created file
print("Destination path:", dest)
```

**Output:** 

```py
After copying file:
['input.txt', 'GeeksForGeeks', 'output.txt', 'file.txt', 'web.py', 'tree.cpp']
Destination path: /home/User/Desktop/file.txt
```

**代码#3:** 使用 shutil.copy2()方法时可能出现的错误

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method

# importing shutil module
import shutil

# If the source and destination
# represents the same file
# 'SameFileError' exception
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
shutil.copy2(source, destination)
```

**Output:** 

```py
Traceback (most recent call last):
  File "try.py", line 26, in 
    dest = shutil.copy(source, destination)
  File "/usr/lib/python3.6/shutil.py", line 241, in copy2
    copyfile(src, dst, follow_symlinks=follow_symlinks)
  File "/usr/lib/python3.6/shutil.py", line 104, in copyfile
    raise SameFileError("{!r} and {!r} are the same file".format(src, dst))
shutil.SameFileError: '/home/User/Desktop/file.txt' and  '/home/User/Desktop/file.txt'
are the same file
```

**代码#4:** 使用 shutil.copy2()方法时处理错误

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method

# importing shutil module
import shutil

# Source path
source = "/home/User/Documents/file.txt"

# Destination path
destination = "/home/User/Documents/file.txt"

# Copy the content of
# source to destination

try:
    shutil.copy2(source, destination)
    print("File copied successfully.")

# If source and destination are same
except shutil.SameFileError:
    print("Source and destination represents the same file.")

# If there is any permission issue
except PermissionError:
    print("Permission denied.")

# For other errors
except:
    print("Error occurred while copying file.")
```

**Output:** 

```py
Source and destination represents the same file.
```

**参考:**T2https://docs.python.org/3/library/shutil.html