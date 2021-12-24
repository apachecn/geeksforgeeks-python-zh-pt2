# Python | sys . getallocatedblock()方法

> 原文:[https://www . geesforgeks . org/python-sys-getallocatedblock-method/](https://www.geeksforgeeks.org/python-sys-getallocatedblocks-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

**`sys.getallocatedblocks()`** 用于获取解释器当前分配的内存块数量，而不考虑其大小。这个函数主要用于跟踪和调试内存泄漏。为了获得更可预测的结果，我们可能不得不调用`_clear_type_cache()`和`gc.collect()`。

> **语法:**sys . getallocatedblock()
> **参数:**此方法不接受参数。
> **返回值:**该方法返回解释器当前分配的内存块数，但如果不能合理计算该信息，则返回 0。

**示例#1 :**

使用`sys.getallocatedblocks()`方法查找分配给解释器的内存。

```py
# Python program to explain sys.getallocatedblocks() method 

# Importing sys module 
import sys 

# Using sys.getallocatedblocks() method
memory = sys.getallocatedblocks()

# Print result
print(memory) 
```

**Output:**

```py
20731

```