# Python | sys . getswitch interval()方法

> 原文:[https://www . geesforgeks . org/python-sys-getswitch interval-method/](https://www.geeksforgeeks.org/python-sys-getswitchinterval-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

`sys.getswitchinterval()`方法用于获取解释器的线程切换间隔(以秒为单位)。这个浮点值决定了分配给并发运行的 Python 线程的**时间片**的理想持续时间。

> **语法:** sys.getswitchinterval()
> 
> **参数:**该方法不接受参数。
> 
> **返回值:**返回解释器的线程切换间隔。

**示例#1 :**

```py
# Python program to explain sys.getswitchinterval() method 

# Importing sys module 
import sys 

# Using sys.getswitchinterval() method 
# to find the interpreter’s thread switch interval
interval = sys.getswitchinterval()

# Print result 
print(interval) 

```

**Output:**

```py
0.005

```