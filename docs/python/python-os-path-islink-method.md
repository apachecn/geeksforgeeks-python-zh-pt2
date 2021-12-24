# Python | os.path.islink()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-islink-method/](https://www.geeksforgeeks.org/python-os-path-islink-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.islink()***`方法用于检查给定的路径是否代表一个现有的目录条目，该条目是否是符号链接。

**注意:**如果 Python 运行时不支持符号链接，那么`***os.path.islink()***`方法总是返回 *False* 。

> ***语法:*** os.path.islink(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果给定的路径是一个符号链接的目录条目，该方法返回*真*，否则返回*假*。

**创建软链接或符号链接**
在 Unix 或 Linux 中，可以使用命令中的**创建软链接或符号链接。以下是在 shell 提示符下创建符号链接的语法:**

```
$ ln -s {source-filename} {symbolic-filename}

```

示例:
![create symbolic link ](img/5861c946e3e902b77ecd251ccedc352f.png)

在上面的输出中，*文件(快捷方式)。txt* 是一个符号链接，也显示了它所链接的文件名。

**代码:**使用 os.path.islink()方法检查给定路径是否为符号链接

```
# Python program to explain os.path.islink() method 

# importing os.path module 
import os.path

# Path 
path = "/home/ihritik/Documents/file(original).txt"

# Check whether the 
# given path is a
# symbolic link
isLink = os.path.islink(path)
print(isLink)

# Path
path = "/home/ihritik/Desktop/file(shortcut).txt"

# Check whether the 
# given path is a
# symbolic link
isLink = os.path.islink(path)
print(isFile)
```

**Output:**

```
False
True

```

**参考:**T2】https://docs.python.org/3/library/os.path.html