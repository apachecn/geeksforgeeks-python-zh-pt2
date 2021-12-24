# Python | time.time()方法

> 原文:[https://www.geeksforgeeks.org/python-time-time-method/](https://www.geeksforgeeks.org/python-time-time-method/)

**Python 中的时间模块**提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。

**时间模块**的`***time.time()***`方法用于获取自纪元以来的时间，单位为秒。闰秒的处理依赖于平台。

**注:**纪元是时间开始的点，与平台有关。在 Windows 和大多数 Unix 系统上，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)，闰秒不会计入自纪元以来的秒数。要查看给定平台上的纪元，我们可以使用`***time.gmtime(0)***`。

> **语法:** time.time()
> 
> **参数:**不需要参数
> 
> **返回类型:**该方法返回一个浮点值，表示自纪元以来的时间(以秒为单位)。

**代码#1:** 使用`***time.time()***`方法

```
# Python program to explain time.time() method

# importing time module
import time

# Get the epoch
obj = time.gmtime(0)
epoch = time.asctime(obj)
print("epoch is:", epoch)

# Get the time in seconds
# since the epoch
time_sec = time.time()

# Print the time 
print("Time in seconds since the epoch:", time_sec)
```

**输出:**

```
epoch is: Thu Jan  1 00:00:00 1970
Time in seconds since the epoch: 1566454995.8361387

```

**代码#2:** 计算两个日期之间的秒数

```
# Python program to explain time.time() method

# importing time module
import time

# Date 1
date1 = "1 Jan 2000 00:00:00"

# Date 2
# Current date
date2 = "22 Aug 2019 00:00:00"

# Parse the date strings
# and convert it in 
# time.struct_time object using
# time.strptime() method
obj1 = time.strptime(date1, "% d % b % Y % H:% M:% S")
obj2 = time.strptime(date2, "% d % b % Y % H:% M:% S")

# Get the time in seconds
# since the epoch
# for both time.struct_time objects
time1 = time.mktime(obj1)
time2 = time.mktime(obj2)

print("Date 1:", time.asctime(obj1))
print("Date 2:", time.asctime(obj2))

# Seconds between Date 1 and date 2
seconds = time2 - time1
print("Seconds between date 1 and date 2 is % f seconds" % seconds)
```

**输出:**

```
Date 1: Sat Jan  1 00:00:00 2000
Date 2: Thu Aug 22 00:00:00 2019
Seconds between date 1 and date 2 is 619747200.000000 seconds

```

**参考:**T2】https://docs.python.org/3/library/time.html#time.time