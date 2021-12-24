# Python 中的 PYTHONPATH 环境变量

> 原文:[https://www . geeksforgeeks . org/python path-环境-python 中的变量/](https://www.geeksforgeeks.org/pythonpath-environment-variable-in-python/)

Python 的行为受其环境变量的影响很大。其中一个变量是 PYTHONPATH。它用于设置用户定义模块的路径，以便可以直接导入到 Python 程序中。它还负责处理 Python 模块的默认搜索路径。PythonPATH 变量保存一个字符串，该字符串包含需要由 PYTHON 添加到 sys.path 目录列表中的各种目录的名称。该变量的主要用途是允许用户导入尚未安装的模块。让我们试着用一个例子来理解这个概念。

假设你定义了一个模块如下:

```py
# user-defined module
# saved as my_module.py

def module_func():
    print("You just imported the user-defined module")
```