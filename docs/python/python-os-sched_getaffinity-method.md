# Python | os.sched_getaffinity()方法

> 原文:[https://www . geesforgeks . org/python-OS-sched _ getaffinity-method/](https://www.geeksforgeeks.org/python-os-sched_getaffinity-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.sched_getaffinity()***`Python 中的方法用于获取具有指定进程 id 的进程有资格在其上运行的那组 CPU。

**注意:**此方法仅在部分 UNIX 平台上可用。

> ***语法:***OS . sched _ getaffinity(PID)
> 
> ***参数:***
> **pid** :需要 CPU 亲和掩码的进程的进程 id。进程的 CPU 相似性掩码决定了它有资格运行的一组 CPU。
> PID 为 0 代表调用过程。
> 
> ***返回类型:*** 该方法返回一个代表 CPU 的 set 对象，具有指定进程 id 的进程可以在该对象上运行。

**Code:** Use of os.sched_getaffinity() method

```py
# Python program to explain os.sched_getaffinity() method  

# importing os module 
import os

# Get the set of CPUs
# on which the calling process
# is eligible to run.

# 0 as pid represents the
# calling process
pid = 0
affinity = os.sched_getaffinity(pid)

# Print the result
print(affinity)

# Change the CPU affinity mask
# of the calling process
# using os.sched_setaffinity() method

# Below CPU affinity mask will
# restrict a process to only
# these 2 CPUs (0, 1) i.e process can
# run on these CPUs only
affinity_mask = {0, 1}
pid = 0
os.sched_setaffinity(0, affinity_mask)

# Now again, Get the set of CPUs
# on which the calling process
# is eligible to run.
pid = 0
affinity = os.sched_getaffinity(pid)

# Print the result
print(affinity)
```

**Output:**

```py
{0, 1, 2, 3}
{0, 1}

```

**参考文献:**

*   [https://docs . python . org/3/library/OS . html # OS . sched _ getaffinity](https://docs.python.org/3/library/os.html#os.sched_getaffinity)
*   [https://linux.die.net/man/2/sched_getaffinity](https://linux.die.net/man/2/sched_getaffinity)