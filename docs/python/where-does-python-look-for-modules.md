# Python 在哪里寻找模块？

> 原文:[https://www . geesforgeks . org/python 在哪里查找模块/](https://www.geeksforgeeks.org/where-does-python-look-for-modules/)

模块只是一条 python。py 文件，我们可以在另一个文件中使用函数、类和变量。要在另一个文件中使用这些东西，我们需要先在那个文件中导入那个模块，然后才能使用它们。模块可以存在于不同的目录中。

在本文中，我们将讨论 python 在哪里查找模块。

Python 分三步寻找模块:-

1.  首先，它在当前目录中搜索。
2.  如果没有找到，那么它在外壳变量[中的目录中搜索](https://www.geeksforgeeks.org/pythonpath-environment-variable-in-python/)
3.  如果同样失败，python 会检查安装 Python 时配置的安装相关目录列表

现在我们将讨论这些步骤:

**第一步:**首先 python 在当前目录中搜索。从当前目录来看，我们指的是调用模块的文件所在的目录。我们可以通过 [os.getcwd()](https://www.geeksforgeeks.org/python-os-getcwd-method/) 方法从 python 的 [os](https://www.geeksforgeeks.org/os-module-python-examples/) 模块查看工作目录。从该方法返回的目录称为当前目录。获取当前目录的代码是:

## 计算机编程语言

```py
# importing os module
import os       

# printing the current working directory
print(os.getcwd())
```

上述代码的输出将是当前工作目录，将首先搜索要导入的模块。

**步骤 2:** 如果在当前目录中没有找到需要导入的模块。然后 python 将在目录名列表 PYTHONPATH 中搜索它，语法与 shell 变量 PATH 相同。要知道 PYTHONPATH 中的目录，我们只需通过[系统](https://www.geeksforgeeks.org/python-sys-module/)模块获取它们。[系统路径](https://www.geeksforgeeks.org/sys-path-in-python/)为我们提供了模块需要导入时将被搜索的所有路径的列表。要查看这些目录，我们必须编写以下代码:

## 计算机编程语言

```py
# importing the sys module
import sys        

# printing sys.path variable of sys module
print(sys.path)
```

**Output**[‘/home’, ‘/usr/lib/python2.7’, ‘/usr/lib/python2.7/plat-x86_64-linux-gnu’, ‘/usr/lib/python2.7/lib-tk’, ‘/usr/lib/python2.7/lib-old’, ‘/usr/lib/python2.7/lib-dynload’, ‘/usr/local/lib/python2.7/dist-packages’, ‘/usr/lib/python2.7/dist-packages’] 

**第 3 步:**如果在以上 2 步中没有找到该模块，python 解释器会尝试在安装 python 时配置的安装相关目录列表中找到它。这些目录也包含在 [sys](https://www.geeksforgeeks.org/python-sys-module/) 模块的 [sys.path](https://www.geeksforgeeks.org/sys-path-in-python/) 变量中，可以通过与上述步骤相同的方式获知。代码将是:

## 计算机编程语言

```py
# importing the sys module
import sys        

# printing sys.path variable of sys module
print(sys.path)
```

**Output**[‘/home’, ‘/usr/lib/python2.7’, ‘/usr/lib/python2.7/plat-x86_64-linux-gnu’, ‘/usr/lib/python2.7/lib-tk’, ‘/usr/lib/python2.7/lib-old’, ‘/usr/lib/python2.7/lib-dynload’, ‘/usr/local/lib/python2.7/dist-packages’, ‘/usr/lib/python2.7/dist-packages’]