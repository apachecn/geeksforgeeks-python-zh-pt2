# Python | os.mknod()方法

> 原文:[https://www.geeksforgeeks.org/python-os-mknod-method/](https://www.geeksforgeeks.org/python-os-mknod-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***OS . mknod()***Python 中的方法用于创建文件系统节点，即具有指定路径名的文件、设备专用文件或命名管道。

> **语法:** os.mknod(路径，模式= 0o600，设备= 0，* dir _ FD =无)
> **参数:**
> **路径:**表示文件系统路径的类路径对象。
> **设备**(可选):定义新创建的设备文件。此参数的默认值为 0。
> **dir_fd** (可选):这是一个引用目录的文件描述符。
> **返回类型:**此方法不返回任何值。

**代码:**使用 ***os.mknod()*** 方法

## 蟒蛇 3

```
# Python3 program to explain os.mknod() method

# importing os module
import os

# importing stat module
import stat

# Path
path = "filex.txt"

# Permission to use
per = 0o600

# type of node to be created
node_type = stat.S_IRUSR
mode = per | node_type

# Create a file system node
# with specified permission
# and type using
# os.mknod() method
os.mknod(path, mode)

print("Filesystem node is created successfully")
```

**Output:** 

```
File system node is created successfully
```