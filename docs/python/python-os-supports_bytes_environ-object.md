# python | OS . support _ bytes _ about object

> 原文:[https://www . geesforgeks . org/python-OS-supports _ bytes _ environ-object/](https://www.geeksforgeeks.org/python-os-supports_bytes_environ-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.supports_bytes_environ***`检查环境的本机操作系统类型是否为*字节*。例如，*窗口*没有*字节*作为环境的本机操作系统类型。所以它的值在*窗口*上为假。

> ***语法:***OS . supports _ bytes _ 约
> 
> ***参数:*** 是不可调用对象。因此，不需要任何参数。
> 
> ***返回类型:*** 该对象根据环境的本机操作系统类型是否为字节，返回布尔值 True 或 False。

**Code:** Use of os.supports_bytes_environ to check whether native OS type of the environment is bytes or not.

```py
# Python program to explain os.supports_bytes_environ object 

# importing os module 
import os

# check whether the native
# OS type of the environment
# is bytes or not.
isBytes = os.supports_bytes_environ

# Print result
print(isBytes)
```

**Output:**

```py
True

```