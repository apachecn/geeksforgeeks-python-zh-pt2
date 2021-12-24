# Python | time.time_ns()方法

> 原文:[https://www.geeksforgeeks.org/python-time-time_ns-method/](https://www.geeksforgeeks.org/python-time-time_ns-method/)

Python 中的时间模块提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。

**时间模块**的`***time.time_ns()***`方法用于获取自历元以来的时间，单位为纳秒。要得到纪元以来的时间(以秒为单位)，我们可以使用 [`***time.time()***`](https://www.geeksforgeeks.org/python-time-time-method/) 方法。

纪元是时间开始的点，并且依赖于平台。在 Windows 和大多数 Unix 系统上，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)，闰秒不会计入自纪元以来的秒数。为了检查给定平台上的纪元是什么，我们可以使用 time.gmtime(0)。

**注意:** `***time.time_ns()***`方法在 Python 版本中是新的

> **语法:**
> time.time_ns()
> 
> **参数:**
> 不需要参数。
> 
> **返回类型:**
> 该方法返回一个整数值
> 表示自纪元以来的时间，单位为纳秒。

**代码:**使用`***time.time_ns()***`方法

```py
# Python program to explain time.time_ns() method 

# importing time module 
import time 

# Get the epoch 
obj = time.gmtime(0) 
epoch = time.asctime(obj) 
print("epoch is:", epoch) 

# Get the time in seconds 
# since the epoch 
# using time.time() method
time_sec = time.time() 

# Get the time in nanoseconds
# since the epoch
# using time.time_ns() method
time_nanosec = time.time_ns()

# Print the time 
# in seconds since the epoch 
print("Time in seconds since the epoch:", time_sec) 

# Print the time 
# in nanoseconds since the epoch 
print("Time in nanoseconds since the epoch:", time_nanosec) 
```

**Output:**

```py
epoch is: Thu Jan  1 00:00:00 1970
Time in seconds since the epoch: 1567451658.4676464
Time in nanoseconds since the epoch: 1567451658467647709

```

**参考文献:**T2】https://docs.python.org/3/library/time.html#time.time_ns