# Python | os.getloadavg()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getloadavg-method/](https://www.geeksforgeeks.org/python-os-getloadavg-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.getloadavg()***`方法用于获取最近 1 分钟、5 分钟和 15 分钟的负载平均值。负载平均值是系统运行队列中的进程数在 1、5 和 15 分钟内的平均值。如果无法获得平均负荷，此方法将提高*误差*。

**注意:**此方法仅在 UNIX 平台上可用。

> ***语法*** os.getloadavg()
> 
> ***参数:*** 不需要参数。
> 
> ***返回类型:*** 这个方法返回一个由浮点值组成的元组对象，表示过去 1、5 和 15 分钟的平均负载。

**Code:** Use of os.getloadavg() method to get the load average over the last 1, 5, and 15 minutes.

```py
# Python program to explain os.getloadavg() method  

# importing os module 
import os

# Get the load average over
# the last 1, 5, and 15 minutes 
# using os.getloadavg() method
load1, load5, load15 = os.getloadavg()

# Print the load average over
# the last 1, 5, and 15 minutes 
print("Load average over the last 1 minute:", load1)
print("Load average over the last 5 minute:", load5)
print("Load average over the last 15 minute:", load15)
```

**Output:**

```py
Load average over the last 1 minute: 0.34
Load average over the last 5 minute: 0.42
Load average over the last 15 minute: 0.46

```