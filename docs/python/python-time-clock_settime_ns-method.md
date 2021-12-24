# Python | time . clock _ settime _ ns()方法

> 原文:[https://www . geesforgeks . org/python-time-clock _ set time _ ns-method/](https://www.geeksforgeeks.org/python-time-clock_settime_ns-method/)

**时间模块**的`***time.clock_settime_ns()***`方法用于设置指定时钟`clk_id`的时间(以纳秒为单位)。基本上， *clk_id* 是代表时钟 id 的整数值。该方法类似于`***time.clock_settime()***`方法，用于设置指定时钟 *clk_id* 的时间，但以分数秒为单位。

> **语法:**time . clock _ settime _ ns(clk _ id，纳秒)
> 
> **参数:**
> **clk_id:** 一个 clk_id 常量或代表时钟 clk_id 的整数值。
> 
> **返回类型:**此方法不返回值。

**代码:**使用`***time.clock_settime_ns()***`方法

```
# Python program to explain time.clock_settime_ns() method

# importing time module
import time

# clk_id for System-wide real-time clock
clk_id = time.CLOCK_REALTIME

# Get the current value of
# system-wide real-time clock (in nanoseconds)
# using time.clock_gettime_ns() method
t = time.clock_gettime_ns(clk_id) 

print("Current value of system-wide real-time clock: % d nanoseconds" % t)

# Set the new value of
# time (in nanoseconds) for
# System-wide real-time clock
# using time.clock_settime_ns() method
nanosecs = 10000000
time.clock_settime(clk_id, nanosecs)

print("\nTime  modified")

# Get the modified value of
# system-wide real-time clock (in nanoseconds)
# using time.clock_gettime_ns() method
t = time.clock_gettime_ns(clk_id) 
print("\nCurrent value of system-wide real-time clock: % d nanoseconds" % t)
```

**Output:**

```
Current value of system-wide real-time clock: 1568621304462590132 nanoseconds

Time  modified

Current value of system-wide real-time clock: 10000000000180111 nanoseconds

```

**参考:**[https://docs . python . org/3/library/time . html # time . clock _ settime _ ns](https://docs.python.org/3/library/time.html#time.clock_settime_ns)