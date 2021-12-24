# Python | os.sched_setaffinity()方法

> 原文:[https://www . geesforgeks . org/python-OS-sched _ set affinity-method/](https://www.geeksforgeeks.org/python-os-sched_setaffinity-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.sched_setaffinity()***`Python 中的方法用于设置指定进程 id 所指示的进程的 CPU 亲缘关系掩码。进程的 CPU 相似性掩码决定了它可以运行的 CPU 集。

**注意:**此方法仅在部分 UNIX 平台上可用。

> ***语法:***OS . sched _ setaffinity(PID，mask)
> 
> ***参数:***
> **pid** :需要设置 CPU 亲和掩码的进程的进程 id。进程的 CPU 相似性掩码决定了它有资格运行的一组 CPU。
> PID 为 0 代表调用过程。
> **掩码**:一组整数，表示进程应该被限制到的一组 CPU。
> 
> ***返回类型:*** 此方法不返回值。

**Code:** Use of os.sched_setaffinity() method

```
# Python program to explain os.sched_setaffinity() method  

# importing os module 
import os

# Get the number of CPUs
# in the system
# using os.cpu_count() method
print("Number of CPUs:", os.cpu_count())

# Get the set of CPUs
# on which the calling process
# is eligible to run. using
# os.sched_getaffinity() method
# 0 as PID represents the
# calling process
pid = 0
affinity = os.sched_getaffinity(pid)

# Print the result
print("Process is eligible to run on:", affinity)

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
print("CPU affinity mask is modified for process id % s" % pid) 

# Now again, Get the set of CPUs
# on which the calling process
# is eligible to run.
pid = 0
affinity = os.sched_getaffinity(pid)

# Print the result
print("Now, process is eligible to run on:", affinity)
```

**Output:**

```
Number of CPUs: 4
Process is eligible to run on: {0, 1, 2, 3}
CPU affinity mask is modified for process id 0
Now, process is eligible to run on: {0, 1}

```

**参考文献:**

*   [https://docs . python . org/3/library/OS . html # OS . sched _ set affinity](https://docs.python.org/3/library/os.html#os.sched_setaffinity)
*   [https://linux.die.net/man/2/sched_getaffinity](https://linux.die.net/man/2/sched_getaffinity)