# Python | time.clock_gettime()方法

> 原文:[https://www . geesforgeks . org/python-time-clock _ gettime-method/](https://www.geeksforgeeks.org/python-time-clock_gettime-method/)

**时间模块**的`***time.clock_gettime()***`方法用于获取指定时钟 clk_id 的时间。基本上， *clk_id* 是代表时钟 id 的整数值。

以下是 UNIX 平台上可用的常量，可用作 *clk_id* 参数的值:

| clk_id | clk_id 常数 | 意义 |
| **0** | **时间。时钟 _ 实时** | 全系统实时时钟 |
| **1** | **时间。时钟 _ 进程 _CPUTIME_ID** | 来自中央处理器的高分辨率每进程计时器 |
| **2** | **时间。时钟 _ 单调** | 它表示从某个未指定的起点开始的单调时间 |
| **3** | **时间。时钟 _ 线程 _CPUTIME_ID** | 线程特定的中央处理器时间时钟 |
| **4** | **时间。时钟 _ 单调 _ 原始** | 类似于时间。时钟单调，但提供对基于硬件的原始时间的访问，不受 NTP 调整的影响 |

**注意:** `***time.clock_gettime()***`方法只在类 UNIX 系统上可用。

> **语法:** time.clock_gettime(clk_id)
> 
> **参数:**
> **clk_id:** 一个 clk_id 常量或代表时钟 clk_id 的整数值。
> 
> **返回类型:**该方法返回一个浮点值，代表指定时钟 clk_id 的时间(以秒为单位)。

**代码#1:** 使用`***time.clock_gettime()***`方法

```py
# Python program to explain time.clock_gettime() method

# importing time module
import time

# clk_id for System-wide real-time clock
clk_id1 = time.CLOCK_REALTIME

# clk_id for monotonic clock
clk_id2 = time.CLOCK_MONOTONIC

# clk_id for monotonic (Raw hardware
# based time) clock
clk_id3 = time.CLOCK_MONOTONIC

# clk_id for Thread-specific CPU-time clock
clk_id4 = time.CLOCK_THREAD_CPUTIME_ID

# clk_id for High-resolution
# per-process timer from the CPU
clk_id5 = time.CLOCK_PROCESS_CPUTIME_ID

# Get the time (in seconds) of the above 
# specified clock clk_ids
# using time.clock_gettime() method
t1 = time.clock_gettime(clk_id1)
t2 = time.clock_gettime(clk_id2)
t3 = time.clock_gettime(clk_id3)
t4 = time.clock_gettime(clk_id4)
t5 = time.clock_gettime(clk_id5)

# Print the time (in seconds) of 
# different clock clk_ids
print("Value of system-wide real-time clock time:", t1)
print("Value of monotonic clock time:", t2)
print("Value of monotonic (raw-hardware based) clock time:", t3)
print("Value of thread-specific CPU time clock:", t4)
print("Value of per-process timer from the CPU:", t5)  

```

**Output:**

```py
Value of system-wide real-time clock time: 1568586677.79805
Value of monotonic clock time: 11754.867643594
Value of monotonic (raw-hardware based) clock time: 11754.867644148
Value of thread-specific CPU time clock: 0.03590527
Value of per-process timer from the CPU: 0.035907437

```

**代码#2:** 使用整数值作为`***time.clock_gettime()***`方法的参数

```py
# Python program to explain time.clock_gettime() method

# importing time module
import time

# value of clk_id for time.CLOCK_REALTIME
# clock id constant which represents
# System-wide real-time clock is 0
clk_id1 = 0

# value of clk_id for time.CLOCK_MONOTONIC
# clock id constant which represents
# a monotonic clock is 2
clk_id2 = 2

# Get the time (in seconds)
# for the specified clock clk_ids
# using time.clock_gettime() method
t1 = time.clock_gettime(clk_id1)
t2 = time.clock_gettime(clk_id2)

# Print the time in seconds
print("Value of system-wide real-time clock time:", t1)
print("Value of monotonic clock time:", t2)
```

**Output:**

```py
Value of system-wide real-time clock time: 1568587204.9810832
Value of monotonic clock time: 12282.050676627

```

**参考:**[https://docs . python . org/3/library/time . html # time . clock _ gettime](https://docs.python.org/3/library/time.html#time.clock_gettime)