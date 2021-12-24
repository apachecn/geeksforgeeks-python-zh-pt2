# Python | os.path.splitdrive()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-split drive-method/](https://www.geeksforgeeks.org/python-os-path-splitdrive-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常见的路径名操作。

Python 中的`***os.path.splitdrive()***`方法用于将路径名拆分成一对*驱动*和*尾部*。这里*驱动*或者是挂载点，或者空弦静止路径组件是*尾*。

在不使用驱动规格的系统上，*驱动*将始终为空字符串。例如:UNIX。

在 Windows 上，`***os.path.splitdrive()***`方法将给定的路径名拆分为驱动器或 UNC sharepoint 作为*驱动器*和其他路径组件作为*尾部*。
**例如:**

```py
     path name                         drive                  tail
On Windows
If path contains drive letter
C:\User\Documents\file.txt               C:           C:\User\Documents\file.txt

If the path contains UNC path 
\\host\computer\dir\file.txt       \\host\computer          \dir\file.txt

On Unix
/home/User/Documents/file.txt         {empty}        /home/User/Documents/file.txt   

```

> ***语法:*** os.path.splitdrive(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个元组，表示给定路径名的驱动器和尾部。

**Code #1:** Use of os.path.splitdrive() method (On Windows)

```py
# Python program to explain os.path.splitdrive() method 

# importing os module 
import os

# Path Containing a drive letter 
path = R"C:\User\Documents\file.txt"

# Split the path in 
# drive and tail pair
drive_tail = os.path.splitdrive(path)

# print drive and tail
# of the given path
print("Drive of path '%s:'" %path, drive_tail[0])
print("Tail of path '%s:'" %path, drive_tail[1], "\n")

# Path representing a UNC path 
path = R"\\host\computer\dir\file.txt"

# Split the path in 
# drive and tail pair
drive_tail = os.path.splitdrive(path)

# print drive and tail
# of the given path
print("Drive of path '%s':" %path, drive_tail[0])
print("Tail of path '%s':" %path, drive_tail[1], "\n")

# Path representing a relative path 
path = R"\dir\file.txt"

# Split the path in 
# drive and tail pair
drive_tail = os.path.splitdrive(path)

# print drive and tail
# of the given path
print("Drive of path '%s':" %path, drive_tail[0])
print("Tail of path '%s':" %path, drive_tail[1])
```

**Output:**

```py
Drive of path 'C:\User\Documents\file.txt': C:
Tail of path 'C:\User\Documents\file.txt': \User\Documents\file.txt 

Drive of path '\\host\computer\dir\file.txt': \\host\computer 
Tail of path '\\host\computer\dir\file.txt': \dir\file.txt 

Drive of path '\dir\file.txt':  
Tail of path '\dir\file.txt': \dir\file.txt 

```

**代码#2:** 使用`os.path.splitdrive()`方法(在 UNIX 上)

```py
# Python program to explain os.path.splitdrive() method 

# importing os module 
import os

# Path
path = "/home/User/Documents/file.txt"

# Split the path in 
# drive and tail pair
drive_tail = os.path.splitdrive(path)

# print drive and tail
# of the given path
print("Drive of path '%s':" %path, drive_tail[0])
print("Tail of path '%s':" %path, drive_tail[1])

# os.path.splitdrive() method
# will return drive as empty everytime
# as UNIX do not use
# drive specification
```

**Output:**

```py
Drive of path '/home/User/Documents/file.txt': 
Tail of path '/home/User/Documents/file.txt': /home/User/Documents/file.txt

```

**参考:**T2】https://docs.python.org/3/library/os.path.html