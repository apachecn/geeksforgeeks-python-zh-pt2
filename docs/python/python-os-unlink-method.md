# Python | os.unlink()方法

> 原文:[https://www.geeksforgeeks.org/python-os-unlink-method/](https://www.geeksforgeeks.org/python-os-unlink-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.unlink()***`方法用于移除或删除文件路径。该方法在语义上与 [os.remove()](https://www.geeksforgeeks.org/python-os-remove-method/) 方法相同。
和`***os.remove()***`一样，方法它也不能删除目录。如果给定的路径是一个目录，那么 **IsADirectoryError** 异常将由这个方法引发。`***[os.rmdir()](https://www.geeksforgeeks.org/python-os-rmdir-method/)***`方法可以用来删除一个目录。

> ***语法:*** os.unlink(路径，*，dir_fd =无)
> 
> ***参数:***
> **路径**:代表文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd** (可选) :引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.unlink() method to remove or delete a file path

```
# Python program to explain os.unlink() method 

# importing os module 
import os

# File Path
path = "/home / ihritik / Documents / file1.txt"

# Remove the file path
# using os.unlink() method
os.unlink(path)

print("File path has been removed successfully")
```

**Output:**

```
File path has been removed successfully

```

**Code #2:** If the given path is a directory

```
# Python program to explain os.unlink() method 

# importing os module 
import os

# Path
path = "/home / User / Documents / ihritik"

# if the given path 
# is a directory then 
# 'IsADirectoryError' exception
# will raised 

# Remove the given
# file path
os.unlink(path)
print("File path has been removed successfully")

# Similarly, if the specified
# file path does not exists or  
# is invalid then corresponding
# OSError will be raised
```

**Output:**

```
Traceback (most recent call last):
  File "unlink.py", line 17, in 
    os.unlink(path)
IsADirectoryError: [Errno 21] Is a directory: '/home/User/Documents/ihritik'

```

**Code #3:** Handling errors while using os.unlink() method

```
# Python program to explain os.unlink() method 

# importing os module 
import os

# path
path = '/home / User / Documents / ihritik'

# Try Removing the given 
# file path using
# try and except block 
try:
    os.unlink(path)
    print("File path removed successfully")

# If the given path is 
# a directory
except IsADirectoryError:
    print("The given path is a directory")

# If path is invalid
# or does not exists
except FileNotFoundError :
    print("No such file or directory found.")

# If the process has not
# the permission to remove
# the given file path 
except PermissionError:
    print("Permission denied")

# For other errors
except :
    print("File can not be removed")
```

**Output:**

```
The given path is a directory

```

**参考:**T2】https://docs.python.org/3/library/os.html