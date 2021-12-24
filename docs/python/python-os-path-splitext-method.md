# Python | os.path.splitext()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-splitext-method/](https://www.geeksforgeeks.org/python-os-path-splitext-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常见的路径名操作。

Python 中的`***os.path.splitext()***`方法用于将路径名拆分成一对*根*和 *ext* 。这里 *ext* 代表延伸，有指定路径的延伸部分，而*根*是除 *ext* 部分之外的一切。如果指定的路径没有任何扩展名，则
*ext* 为空。如果指定的路径有前导句点('.')，就会被忽略。

例如，考虑以下路径名:

```
      path name                          root                        ext
/home/User/Desktop/file.txt    /home/User/Desktop/file              .txt
/home/User/Desktop             /home/User/Desktop                  {empty}
file.py                               file                          .py
.txt                                  .txt                         {empty}   

```

> ***语法:*** os.path.splitext(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个元组，代表指定路径名的根和外部分。

**Code:** Use of os.path.splitext() method

```
# Python program to explain os.path.splitext() method 

# importing os module 
import os

# path
path = '/home/User/Desktop/file.txt'

# Split the path in 
# root and ext pair
root_ext = os.path.splitext(path)

# print root and ext
# of the specified path
print("root part of '% s':" % path, root_ext[0])
print("ext part of '% s':" % path, root_ext[1], "\n")

# path
path = '/home/User/Desktop/'

# Split the path in 
# root and ext pair
root_ext = os.path.splitext(path)

# print root and ext
# of the specified path
print("root part of '% s':" % path, root_ext[0])
print("ext part of '% s':" % path, root_ext[1])
```

**Output:**

```
root part of '/home/User/Desktop/file.txt': /home/User/Desktop/file
ext part of '/home/User/Desktop/file.txt': .txt 

root part of '/home/User/Desktop/': /home/User/Desktop/
ext part of '/home/User/Desktop/': 

```

**参考:**T2】https://docs.python.org/3/library/os.path.html