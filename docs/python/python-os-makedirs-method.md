# Python | os.makedirs()方法

> 原文:[https://www.geeksforgeeks.org/python-os-makedirs-method/](https://www.geeksforgeeks.org/python-os-makedirs-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
在无效或不可访问的文件名和路径，或其他具有正确类型但不被操作系统接受的参数的情况下，操作系统模块中的所有功能都会引发 **OSError** 。
***OS . make dirs()***方法在 Python 中用于递归创建目录。也就是说，在制作叶目录的时候，如果缺少任何一个中级目录，***OS . make dirs()***方法会全部创建。
例如，考虑以下路径:

```
/home/User/Documents/GeeksForGeeks/Authors/ihritik
```

假设我们想要创建目录“ihritik ”,但是目录“GeeksForGeeks”和“Authors”在路径中不可用。然后 ***os.makedirs()*** 方法会在指定的路径中创建所有不可用/缺失的目录。首先创建“极客”和“作者”，然后创建“个人”目录。

> ***语法:*** os.makedirs(路径，模式= 0o777，exist_ok = False)
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **模式**(可选) :表示新建目录模式的整数值..如果省略该参数，则使用默认值 Oo777。
> **exist_ok** (可选) :该参数使用默认值 False。如果目标目录已经存在，如果其值为 False，则引发一个错误，否则不引发。对于值 True，目录保持不变。
> ***返回类型:*** 此方法不返回任何值。

**代码#1:** 使用 os.makedirs()方法创建目录

## 蟒蛇 3

```
# Python program to explain os.makedirs() method

# importing os module
import os

# Leaf directory
directory = "ihritik"

# Parent Directories
parent_dir = "/home/User/Documents/GeeksForGeeks/Authors"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'ihritik'
os.makedirs(path)
print("Directory '%s' created" %directory)

# Directory 'GeeksForGeeks' and 'Authors' will
# be created too
# if it does not exists

# Leaf directory
directory = "c"

# Parent Directories
parent_dir = "/home/User/Documents/GeeksforGeeks/a/b"

# mode
mode = 0o666

path = os.path.join(parent_dir, directory)

# Create the directory
# 'c'

os.makedirs(path, mode)
print("Directory '%s' created" %directory)

# 'GeeksForGeeks', 'a', and 'b'
# will also be created if
# it does not exists

# If any of the intermediate level
# directory is missing
# os.makedirs() method will
# create them

# os.makedirs() method can be
# used to create a directory tree 
```

**输出:**

```
Directory 'ihritik' created
Directory 'c' created
```

**代码#2:** 使用 os.makedirs()方法时出错

## 蟒蛇 3

```
# Python program to explain os.makedirs() method

# importing os module
import os

# os.makedirs() method will raise
# an OSError if the directory
# to be created already exists

# Directory
directory = "ihritik"

# Parent Directory path
parent_dir = "/home/User/Documents/GeeksForGeeks"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'ihritik'
os.makedirs(path)
print("Directory '%s' created" %directory)
```

**输出:**

```
Traceback (most recent call last):
  File "makedirs.py", line 21, in 
    os.makedirs(path)
  File "/usr/lib/python3.6/os.py", line 220, in makedirs
    mkdir(name, mode)
FileExistsError: [Errno 17] File exists: '/home/User/Documents/GeeksForGeeks/ihritik'
```

**代码#3:** 使用 os.makedirs()方法时处理错误

## 蟒蛇 3

```
# Python program to explain os.makedirs() method

# importing os module
import os

# os.makedirs() method will raise
# an OSError if the directory
# to be created already exists
# But It can be suppressed by
# setting the value of a parameter
# exist_ok as True

# Directory
directory = "ihritik"

# Parent Directory path
parent_dir = "/home/ihritik/Desktop/GeeksForGeeks"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'ihritik'
try:
    os.makedirs(path, exist_ok = True)
    print("Directory '%s' created successfully" %directory)
except OSError as error:
    print("Directory '%s' can not be created")

# By setting exist_ok as True
# error caused due already
# existing directory can be suppressed
# but other OSError may be raised
# due to other error like
# invalid path name
```

**输出:**

```
Directory 'ihritik' created successfully
```

**参考:**T2https://docs.python.org/3/library/os.html