# Python | OS . sched _ get _ priority _ max()方法

> 原文:[https://www . geesforgeks . org/python-OS-sched _ get _ priority _ max-method/](https://www.geeksforgeeks.org/python-os-sched_get_priority_max-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**包含一些为调度程序提供接口的方法，用于控制操作系统如何为进程分配 CPU 时间。Python 中的
`***os.sched_get_priority_max()***`方法用于获取指定调度策略的最大优先级值。

**注意:**此方法仅在部分 UNIX 平台上可用。

> ***语法:***OS . sched _ get _ priority _ max(策略)
> 
> ***参数:***
> **策略**需要最大优先级值的调度策略。
> 以下是可以用作策略参数值的调度策略常数:
> 
> *   **os。SCHED_OTHER** :表示默认的调度策略。
> *   **os。SCHED_BATCH** :它代表了 CPU 密集型进程的调度策略，试图保留计算机其他部分的交互性。
> *   **os。SCHED_IDLE** :代表极低优先级后台任务的调度策略。
> *   **os。SCHED _ 散发**:代表零星服务器程序的调度策略。
> *   **os。SCHED_FIFO** :代表先进先出的调度策略。
> *   **os。SCHED_RR** :代表循环调度策略。
> 
> ***返回类型:*** 该方法返回一个整数值，代表指定调度策略的最大优先级值。

**Code:** Use of os.sched_get_priority_max() method

```py
# Python program to explain os.sched_get_priority_max() method  

# importing os module 
import os

print("Below are the maximum priority\
value for different scheduling policy")

# Get the maximum priority value for
# first In First Out scheduling policy
# os.SCHED_FIFO constant represents 
# first In First Out scheduling policy
priority_max = os.sched_get_priority_max(os.SCHED_FIFO)
print("First In First Out scheduling policy:", priority_max)

# Get the maximum priority value for
# round-robin scheduling policy
# os.SCHED_RR constant represents the
# round-robin scheduling policy
priority_max = os.sched_get_priority_max(os.SCHED_RR)
print("Round-robin scheduling policy:", priority_max)

# Get the maximum priority value for
# the default scheduling policy
# os.SCHED_OTHER constant represents the
# default scheduling policy.
priority_max = os.sched_get_priority_max(os.SCHED_OTHER)
print("Default scheduling policy.:", priority_max)

# Get the maximum priority value 
# for scheduling policy for extremely
# low priority background tasks
# os.SCHED_IDLE constant represents the
# scheduling policy for extremely low
# priority background tasks.
priority_max = os.sched_get_priority_max(os.SCHED_IDLE)
print("Scheduling policy for extremely\
 low priority background tasks:", priority_max)

# Get the maximum priority value 
# for scheduling policy for CPU-intensive
# processes that tries to preserve 
# interactivity on the rest of the computer.
# os.SCHED_BATCH represents the
# scheduling policy for CPU-intensive processes
# that tries to preserve interactivity
# on the rest of the computer
priority_max = os.sched_get_priority_max(os.SCHED_BATCH)
print("Scheduling policy for CPU-intensive processes:", priority_max)
```

**Output:**

```py
Below are the maximum priority value for different scheduling policy
First In First Out scheduling policy: 99
Round-robin scheduling policy: 99
Default scheduling policy.: 0
Scheduling policy for extremely low priority background tasks: 0
Scheduling policy for CPU-intensive processes: 0

```

**参考文献:**[https://docs . python . org/3/library/OS . html # OS . sched _ get _ priority _ max](https://docs.python.org/3/library/os.html#os.sched_get_priority_max)