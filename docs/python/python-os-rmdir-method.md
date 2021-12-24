# Python | os.rmdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-rmdir-method/](https://www.geeksforgeeks.org/python-os-rmdir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.rmdir()***`方法用于移除或删除空目录。**如果指定的路径不是空目录，将引发 OSError** 。

> ***语法:*** os.rmdir(路径，* dir _ FD =无)
> 
> ***参数:***
> **路径**:代表文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd** (可选) :引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.rmdir() method to remove an empty directory

```
# Python program to explain os.rmdir() method 

# importing os module 
import os

# Directory name
directory = "ihritik"

# Parent Directory
parent = "/home/User/Documents"

# Path
path = os.path.join(parent, directory)

# Remove the Directory
# "ihritik"
os.rmdir(path)
print("Directory '%s' has been removed successfully" %directory)
```

**Output:**

```
Directory 'ihritik' has been removed successfully

```

**Code #2:** Handling errors while using os.rmdir() method

```
# Python program to explain os.rmdir() method 

# importing os module 
import os

# Directory name
directory = "ihritik"

# Parent Directory
parent = "/home/User/Documents"

# Path
path = os.path.join(parent, directory)

# Remove the Directory
# "ihritik"
try:
    os.rmdir(path)
    print("Directory '%s' has been removed successfully" %directory)
except OSError as error:
    print(error)
    print("Directory '%s' can not be removed" %directory)

# if the specified path 
# is not an empty directory
# then permission error will
# be raised

# similarly if specified path
# is invalid or is not a 
# directory then corresponding
# OSError will be raised
```

**Output:**

```
[Errno 13] Permission denied: '/home/User/Documents/ihritik'
Directory 'ihritik' can not be removed

```

**参考:**T2】https://docs.python.org/3/library/os.html