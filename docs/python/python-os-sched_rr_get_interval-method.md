# Python | OS . sched _ RR _ get _ interval()方法

> 原文:[https://www . geesforgeks . org/python-OS-sched _ RR _ get _ interval-method/](https://www.geeksforgeeks.org/python-os-sched_rr_get_interval-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
**操作系统模块**包含一些方法，这些方法为调度程序提供了一个接口，用于控制操作系统如何分配进程的 CPU 时间。
***OS . sched _ RR _ get _ interval()***Python 中的方法用于获取指定进程 id 所指示的进程的[循环](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/)量程(以秒为单位)。
**什么是循环量子？**
在循环调度策略中，进程以先进先出的方式进行调度，但被给予有限的 CPU 时间，称为*时间片*或*时间量*。
**注:**此方法仅在部分 UNIX 平台上可用。

> ***语法:***OS . sched _ RR _ get _ interval(PID)
> ***参数:***
> **pid** :需要循环量子值的进程的进程 id。pid 为 0 表示调用过程。
> ***返回类型:*** 该方法返回一个浮点值，代表以秒为单位的循环量程。

**代码:**使用 os.sched_rr_get_interval()方法

## 蟒蛇 3

```py
# Python program to explain os.sched_rr_get_interval() method 

# importing os module
import os

# get the Round-Robin time quantum
# of the current process
# A pid of 0 represents the
# the calling process
pid = 0
quantum = os.sched_rr_get_interval(pid)

# print round robin time quantum
print("Round Robin time quantum (in seconds):", quantum)
```

**Output:** 

```py
Round Robin time quantum (in seconds): 0.016
```

**参考文献:**T2T4】