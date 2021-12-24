# Python | os.remove()方法

> 原文:[https://www.geeksforgeeks.org/python-os-remove-method/](https://www.geeksforgeeks.org/python-os-remove-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.remove()***`方法用于移除或删除文件路径。此方法不能删除目录。如果指定的路径是一个目录，那么方法将引发**错误**。`***os.rmdir()***`可用于删除目录。

> ***语法:*** os.remove(路径，*，dir_fd =无)
> 
> ***参数:***
> **路径**:代表文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd** (可选) :引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.remove() method to remove a file

```
# Python program to explain os.remove() method 

# importing os module 
import os

# File name
file = 'file.txt'

# File location
location = "/home/User/Documents"

# Path
path = os.path.join(location, file)

# Remove the file
# 'file.txt'
os.remove(path)
print("%s has been removed successfully" %file)
```

**Output:**

```
file.txt has been removed successfully

```

**Code #2:** If the specified path is a directory

```
# Python program to explain os.remove() method 

# importing os module 
import os

# Path
path = "/home/User/Documents/ihritik"

# Remove the specified
# file path
os.remove(path)
print("% s has been removed successfully" % file)

# if the specified path 
# is a directory then 
# 'IsADirectoryError' error
# will raised 

# Similarly if the specified
# file path does not exists or  
# is invalid then corresponding
# OSError will be raised
```

**Output:**

```
Traceback (most recent call last):
  File "osremove.py", line 11, in 
    os.remove(path)
IsADirectoryError: [Errno 21] Is a directory: '/home/User/Documents/ihritik'

```

**Code #3:** Handling error while using os.remove() method

```
# Python program to explain os.remove() method 

# importing os module 
import os

# path
path = '/home/User/Documents/ihritik'

# Remove the specified 
# file path
try:
    os.remove(path)
    print("% s removed successfully" % path)
except OSError as error:
    print(error)
    print("File path can not be removed")
```

**Output:**

```
[Errno 21] Is a directory: '/home/User/Documents/ihritik'
File path can not be removed

```

**参考:**T2】https://docs.python.org/3/library/os.html