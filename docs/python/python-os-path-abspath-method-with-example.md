# Python: os.path.abspath()方法，带示例

> 原文:[https://www . geesforgeks . org/python-OS-path-abspath-method-with-example/](https://www.geeksforgeeks.org/python-os-path-abspath-method-with-example/)

**[Python 中的 OS 模块](https://www.geeksforgeeks.org/os-module-python-examples/)** 提供了各种与操作系统交互的方法。它属于 Python 的标准实用程序模块，所以不需要从外部安装。 **[os.path](https://www.geeksforgeeks.org/os-path-module-python/)** 是 os 模块的一个子模块，包含了一些关于路径名的有用功能。路径参数可以是字符串或字节。这里的这些函数用于不同的目的，例如在 Python 中合并、规范化和检索路径名。

根据文档`os.path.abspath()`返回路径名路径的标准化绝对版本，这听起来很奇怪，但它只是意味着这个方法返回路径名作为参数传递给这个函数。

> **语法:** os.path.abspath(路径)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。
> 
> **返回类型:**该方法返回路径名路径的规范化版本。

**例 1:**

```py
# Python program to demonstrate
# os.path.abspath()

import os.path

# file name   
file_name = 'GFG.txt'

# prints the absolute path of current
# working directory with  file name
print(os.path.abspath(file_name))
```

**输出:**

```py
/home/geeks/Desktop/gfg/GFG.txt

```

**例 2:** 该函数也可以在改变当前工作目录后返回归一化路径。

```py
# Python program to demonstrate
# os.path.abspath()

import os

# file name   
file_name = 'GFG.txt'

# change the current working
# directory
os.chdir("/home/geeks/")

# prints the absolute path of current
# working directory with  file name
print(os.path.abspath(file_name))
```

**输出:**

```py
/home/geeks/GFG.txt

```