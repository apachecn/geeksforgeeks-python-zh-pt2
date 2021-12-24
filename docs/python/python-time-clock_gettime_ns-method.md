# Python | time . clock _ gettime _ ns()方法

> 原文:[https://www . geesforgeks . org/python-time-clock _ gettime _ ns-method/](https://www.geeksforgeeks.org/python-time-clock_gettime_ns-method/)

**Python 中的时间模块**提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。

**时间模块**的`***time.clock_gettime_ns()***`方法用于获取指定时钟 clk_id 的时间(以纳秒为单位)。基本上， *clk_id* 是代表时钟 id 的整数值。

以下是 UNIX 平台上可用的常量，可用作 *clk_id* 参数的值:

| clk_id | clk_id 常数 | 意义 |
| **0** | **时间。时钟 _ 实时** | 全系统实时时钟 |
| **1** | **时间。时钟 _ 进程 _CPUTIME_ID** | 来自中央处理器的高分辨率每进程计时器 |
| **2** | **时间。时钟 _ 单调** | 它表示从某个未指定的起点开始的单调时间 |
| **3** | **时间。时钟 _ 线程 _CPUTIME_ID** | 线程特定的中央处理器时间时钟 |
| **4** | **时间。时钟 _ 单调 _ 原始** | 类似于时间。时钟单调，但提供对基于硬件的原始时间的访问，不受 NTP 调整的影响 |

> **语法:** time.clock_gettime(clk_id)
> 
> **参数:**
> **clk_id:** 一个 clk_id 常量或代表时钟 clk_id 的整数值。
> 
> **返回类型:**该方法返回一个浮点值，代表指定时钟 clk_id 的时间，单位为纳秒。

**代码#1:** 使用`***time.clock_gettime_ns()***`方法

```py
# Python program to explain time.clock_gettime_ns() method

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

# Get the time (in nanoseconds) of the above 
# specified clock clk_ids
# using time.clock_gettime_ns() method
t1 = time.clock_gettime_ns(clk_id1)
t2 = time.clock_gettime_ns(clk_id2)
t3 = time.clock_gettime_ns(clk_id3)
t4 = time.clock_gettime_ns(clk_id4)
t5 = time.clock_gettime_ns(clk_id5)

# Print the time (in nanoseconds) of 
# different clock clk_ids
print("System-wide real-time clock time: % d nanoseconds" % t1)
print("Monotonic clock time: % d nanoseconds" % t2)
print("Monotonic (raw-hardware based) clock time: % d nanoseconds" % t3)
print("Thread-specific CPU time clock: % d nanoseconds" % t4)
print("Per-process timer from the CPU: % d nanoseconds" % t5)  
```

**Output:**

```py
System-wide real-time clock time: 1568588052857445167 nanoseconds
Monotonic clock time: 13129927039288 nanoseconds
Monotonic (raw-hardware based) clock time: 13129927039811 nanoseconds
Thread-specific CPU time clock: 27169892 nanoseconds
Per-process timer from the CPU: 27171779 nanoseconds

```

**代码#2:** 使用整数值作为`***time.clock_gettime_ns()***`方法的参数

```py
# Python program to explain time.clock_gettime_ns() method

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

# Get the time in nanoseconds)
# for the specified clock clk_ids
# using time.clock_gettime_ns() method
t1 = time.clock_gettime_ns(clk_id1)
t2 = time.clock_gettime_ns(clk_id2)

# Print the time in nanoseconds
print("System-wide real-time clock time: % d nanoseconds" % t1)
print("Monotonic clock time: % d nanoseconds" % t2)
```

**Output:**

```py
System-wide real-time clock time: 1568588180971305067 nanoseconds
Monotonic clock time: 13258040899143 nanoseconds

```

**参考:**[https://docs . python . org/3/library/time . html # time . clock _ gettime](https://docs.python.org/3/library/time.html#time.clock_gettime)