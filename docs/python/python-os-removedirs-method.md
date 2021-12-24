# Python | os.removedirs()方法

> 原文:[https://www.geeksforgeeks.org/python-os-removedirs-method/](https://www.geeksforgeeks.org/python-os-removedirs-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.removedirs()***`方法用于递归移除目录。如果成功删除指定路径中的叶目录，则`***os.removedirs()***`会尝试连续删除路径中提到的每个父目录，直到出现错误。引发的错误被忽略，因为通常错误是因为要删除的目录不为空而引发的。
例如，考虑以下路径:

```
'/home/User/Documents/foo/bar/baz'

```

在上面的路径中，`***os.removedirs()***`方法将首先尝试移除叶目录，即*‘baz’*。如果叶目录*“baz”*被成功删除，则该方法将尝试删除*“/home/User/Documents/foo/bar”*然后*“/home/User/Documents/foo”*然后*“/home/User/Documents”*，直到出现错误。要删除的目录应该为空。

> ***语法:*** os.removedirs(路径)
> 
> ***参数:***
> **路径**:代表文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.removedirs() method to remove an empty directory tree

```
# Python program to explain os.removedirs() method 

# importing os module 
import os

# Leaf Directory name
directory = "baz"

# Parent Directory
parent = "/home/User/Documents/foo/bar"

# Path
path = os.path.join(parent, directory)

# Remove the Directory
# "baz"
os.removedirs(path)
print("Directory '%s' has been removed successfully" %directory)

# All parent directory
# of 'baz' will be also
# removed if they are empty

```

**Output:**

```
Directory 'baz' has been removed successfully

```

**Code #2:** Possible errors while using os.removedirs() method

```
# Python program to explain os.removedirs() method 

# importing os module 
import os

# If the specified path 
# is not a directory
# then 'NotADirectoryError'
# exception will be raised

# If the specified path 
# is not an empty directory
# then an 'OSError'
# will be raised

# If there is any
# permission issue while
# removing the directory
# then the 'PermissionError'
# exception will be raised

# similarly if specified path
# is invalid an 'OSError'
# will be raised

# Path
path = '/home/User/Documents/ihritik/file.txt'

# Try to remove
# the specified path
os.removedirs(path) 
```

**Output:**

```
Traceback (most recent call last):
  File "removedirs.py", line 33, in 
    os.removedirs(path)
  File "/usr/lib/python3.6/os.py", line 238, in removedirs
    rmdir(name)
NotADirectoryError: [Errno 20] Not a directory: '/home/User/Documents/ihritik/file.txt'

```

**Code #3:** Handling errors while using os.removedirs() method

```
# Python program to explain os.removedirs() method 

# importing os module 
import os

# Path
path = '/home/User/Documents/ihritik/file.txt'

# Try to remove
# the specified path

try:
    os.removedirs(path)
    print("Director removed successfully")

# If path is not a directory
except NotADirectoryError:
    print("Specified path is not a directory.")

# If permission related errors
except PermissionError:
    print("Permission denied.")

# for other errors
except OSError as error:
    print(error)
    print("Directory can not be removed")
```

**Output:**

```
Specified path is not a directory.

```

**参考:**T2】https://docs.python.org/3/library/os.html