# Python | os.path.join()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-join-method/](https://www.geeksforgeeks.org/python-os-path-join-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。**操作系统路径**模块是 Python 中操作系统模块的子模块，用于常见的路径名操作。
***OS . path . join()***方法在 Python 中智能地连接一个或多个路径组件。此方法将各种路径组件串联起来，除了最后一个路径组件之外，每个非空部分后面都有一个目录分隔符(“/”)。如果要连接的最后一个路径组件为空，则在末尾放置一个目录分隔符(“/”)。
如果路径组件表示绝对路径，则所有先前连接的组件都被丢弃，并且连接从绝对路径组件继续。

> ***语法:*** os.path.join(路径，* path)
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。
> ***路径**:表示文件系统路径的类路径对象。它表示要连接的路径组件。
> 类路径对象是表示路径的字符串或字节对象。
> **注意:**python 中函数定义中的特殊语法 [*args](https://www.geeksforgeeks.org/args-kwargs-python/) (此处为* paths)用于向函数传递可变数量的参数。
> ***返回类型:*** 这个方法返回一个代表串联路径组件的字符串。

**代码:**使用 os.path.join()方法连接各种路径组件

## 蟒蛇 3

```py
# Python program to explain os.path.join() method

# importing os module
import os

# Path
path = "/home"

# Join various path components
print(os.path.join(path, "User/Desktop", "file.txt"))

# Path
path = "User/Documents"

# Join various path components
print(os.path.join(path, "/home", "file.txt"))

# In above example '/home'
# represents an absolute path
# so all previous components i.e User / Documents
# are thrown away and joining continues
# from the absolute path component i.e / home.

# Path
path = "/User"

# Join various path components
print(os.path.join(path, "Downloads", "file.txt", "/home"))

# In above example '/User' and '/home'
# both represents an absolute path
# but '/home' is the last value
# so all previous components before '/home'
# will be discarded and joining will
# continue from '/home'

# Path
path = "/home"

# Join various path components
print(os.path.join(path, "User/Public/", "Documents", ""))

# In above example the last
# path component is empty
# so a directory separator ('/')
# will be put at the end
# along with the concatenated value
```

**Output:** 

```py
/home/User/Desktop/file.txt
/home/file.txt
/home
/home/User/Public/Documents/
```

**参考:**T2https://docs.python.org/3/library/os.path.html