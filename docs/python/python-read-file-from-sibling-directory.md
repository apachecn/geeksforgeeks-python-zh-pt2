# Python–从同级目录

读取文件

> 原文:[https://www . geesforgeks . org/python-从同级目录读取文件/](https://www.geeksforgeeks.org/python-read-file-from-sibling-directory/)

在本文中，我们将讨论在 Python 中从同级目录中读取文件的方法。首先，在一个根文件夹中创建两个文件夹，一个文件夹包含 python 文件，另一个包含要读取的文件。下面是字典树:

**目录树:**

```py
root :
|
|__Sibling_1:
|    \__demo.py
|      
|__Sibling_2:
|      \__file.txt
```

![](img/dda6d98bf7519fb2a1fcbd48de7f25ca.png)

这里，兄弟 1 和兄弟 2 是兄弟。我们将讨论从文件中读取数据的方法。我们将使用 os 模块将当前工作目录更改为具有 file.txt 的目录。

**file.txt:**

> 这是需要读取的数据！！

#### 步骤如下:

1.导入 os 模块并将 demo.py 的路径存储在名为 path 的变量中。[OS . path . real path(_ file _ _)](https://www.geeksforgeeks.org/python-os-path-realpath-method/)方法将给出文件 demo.py 所在的路径，该路径将为“D:\ root \ sible _ 1 \ demo . py”。

## 计算机编程语言

```py
# importing os module
import os

# gives the path of demo.py
path = os.path.realpath(__file__)
print(path)
```

**输出:**

```py
'D:\root\Sibling_1\demo.py'
```

2.使用存在 demo.py 的 [os.path.dirname()](https://www.geeksforgeeks.org/python-os-path-dirname-method/) 获取目录，并将其存储在变量 dir 中。

## 计算机编程语言

```py
import os

# gives the path of demo.py
path = os.path.realpath(__file__)

# gives the directory where demo.py
# exists
dir = os.path.dirname(path)
print(dir)
```