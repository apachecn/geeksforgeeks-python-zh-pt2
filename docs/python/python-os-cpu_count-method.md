# Python | os.cpu_count()方法

> 原文:[https://www.geeksforgeeks.org/python-os-cpu_count-method/](https://www.geeksforgeeks.org/python-os-cpu_count-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.cpu_count()***`使用 Python 中的方法获取系统中的 CPU 数量。如果系统中的 CPU 数量不确定，此方法将返回无。

> ***语法:*** os.cpu_count()
> 
> ***参数:*** 不需要参数。
> 
> ***返回类型:*** 该方法返回一个整数值，表示系统中的 CPU 数量。如果 CPU 数量未确定，则不返回任何值。

**Code:** Use of os.cpu_count() method to get the number of CPUs in the system

```py
# Python program to explain os.cpu_count() method  

# importing os module 
import os

# Get the number of CPUs
# in the system using
# os.cpu_count() method
cpuCount = os.cpu_count()

# Print the number of
# CPUs in the system
print("Number of CPUs in the system:", cpuCount)
```

**Output:**

```py
Number of CPUs in the system: 4

```