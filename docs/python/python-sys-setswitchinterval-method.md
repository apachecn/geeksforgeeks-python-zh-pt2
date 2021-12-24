# Python | sys . setswitchinterval()方法

> 原文:[https://www . geesforgeks . org/python-sys-set switch interval-method/](https://www.geeksforgeeks.org/python-sys-setswitchinterval-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

`sys.setswitchinterval()`方法用于设置解释器的线程切换间隔(秒)。这个浮点值决定了分配给并发运行的 Python 线程的时间片的理想持续时间。实际值可以更高，尤其是如果使用长期运行的内部函数或方法。此外，哪个线程在间隔结束时被调度是操作系统的决定。解释器没有自己的调度程序。这决定了解释器检查线程切换的频率。

> **语法:** sys.setswitchinterval(间隔)
> 
> **参数:**
> **间隔:**新切换间隔待设置。
> 
> **返回值:**返回解释器的线程切换间隔。

**示例#1 :**

```
# Python program to explain sys.setswitchinterval() method 

# Importing sys module 
import sys 

# Using sys.getswitchinterval() method 
# to find the current switch interval 
interval = sys.getswitchinterval()

# Print the current switch interval 
print('Before changing, switchinterval =', interval) 

# New interval
interval = 1

# Using sys.setswitchinterval() method 
# to set the interpreter’s thread switch interval
sys.setswitchinterval(interval)

# Using sys.getswitchinterval() method 
# to find the current switch interval 
interval = sys.getswitchinterval()

# Print the current switch interval 
print('After changing, switchinterval =', interval) 
```

**Output:**

```
Before changing, switchinterval = 0.005
After changing, switchinterval = 1.0

```