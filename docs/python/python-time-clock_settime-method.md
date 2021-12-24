# Python | time.clock_settime()方法

> 原文:[https://www . geesforgeks . org/python-time-clock _ set time-method/](https://www.geeksforgeeks.org/python-time-clock_settime-method/)

**时间模块**的`***time.clock_settime()***`方法用于设置指定时钟 clk_id 的时间(秒)。基本上， *clk_id* 是代表时钟 id 的整数值。

> **语法:** time.clock_settime(clk_id，秒)
> 
> **参数:**
> **clk_id:** 一个 clk_id 常量或代表时钟 clk_id 的整数值。
> 
> **返回类型:**此方法不返回值。

**代码:**使用`***time.clock_settime()***`方法

```
# Python program to explain time.clock_settime() method

# importing time module
import time

# clk_id for System-wide real-time clock
clk_id = time.CLOCK_REALTIME

# Get the current value of
# system-wide real-time clock (in seconds)
# using time.clock_gettime() method
t = time.clock_gettime(clk_id) 

print("Current value of system-wide real-time clock: % d seconds" % t)

# Set the new value of
# time (in seconds) for
# System-wide real-time clock
# using time.clock_settime() method
seconds = 10000000
time.clock_settime(clk_id, seconds)

print("\nTime  modified")

# Get the modified value of
# system-wide real-time clock (in seconds)
# using time.clock_gettime() method
t = time.clock_gettime(clk_id) 
print("\nCurrent value of system-wide real-time clock: % d seconds" % t)
```

**Output:**

```
Current value of system-wide real-time clock: 1568589568 seconds

Time  modified

Current value of system-wide real-time clock: 10000000 seconds

```

**参考:**[https://docs . python . org/3/library/time . html # time . clock _ settime](https://docs.python.org/3/library/time.html#time.clock_settime)