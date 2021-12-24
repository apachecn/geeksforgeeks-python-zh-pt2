# Python | time.mktime()方法

> 原文:[https://www.geeksforgeeks.org/python-time-mktime-method/](https://www.geeksforgeeks.org/python-time-mktime-method/)

**时间模块**的`***time.mktime()***`方法用于将 *time.struct_time* 对象或包含对应于 *time.struct_time* 对象的 9 个元素的元组转换为自本地时间中的纪元以来经过的以秒为单位的时间。

该方法是`***[time.localtime()](https://www.geeksforgeeks.org/python-time-localtime-method/)***`的反函数，它将自纪元以来以秒为单位表示的时间转换为本地时间中的 *time.struct_time* 对象。

以下是 time.struct_time 对象中存在的值:

| 索引 | 属性 | 价值观念 |
| **0** | **tm_year** | (例如，1993 年) |
| **1** | TM _ mon | 范围[1，12] |
| **2** | **tm_mday** | 范围[1，31] |
| **3** | **tm_hour** | 范围[0，23] |
| ****4**** | **tm_min** | 范围[0，59] |
| **5** | **tm_sec** | 范围[0，61] |
| **6** | **tm_wday** | 范围[0，6]，星期一是 0 |
| **7** | TM _ yday | 范围[1，366] |
| **8** | **tm_isdst** | 0、1 或-1 |
| **不适用** | **tm_zone** | 时区名称的缩写 |
| **不适用** | **tm_gmtoff** | 世界协调时以东的偏移量(秒) |

**注:**历元是时间开始的点，与平台有关。在 Windows 和大多数 Unix 系统上，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)，闰秒不会计入自纪元以来的秒数。为了检查给定平台上的纪元是什么，我们可以使用 time.gmtime(0)。

> **语法:** time.mktime(t)
> 
> **参数:**
> **t** :一个 *time.struct_time* 对象或者一个包含 9 个元素的元组对应 *time.struct_time* 对象
> 
> **返回类型:**该方法返回一个浮点值，该值代表自纪元以来以秒为单位表示的时间。

**代码#1:** 使用`***time.mktime()***`方法

```
# Python program to explain time.mktime() method 

# importing time module 
import time 

# time.gmtime() method will returns
# a time.struct_time object in UTC
# for the time expressed in seconds
# since the epoch
seconds = 1000000
obj1 = time.gmtime(seconds)

# Print time.struct_time object (in UTC)
print(obj1)

# Convert the time.struct_time
# object to local time expressed in
# seconds since the epoch
# using time.mktime() method
time_sec = time.mktime(obj1)

# Print the local time in seconds
print("\nLocal time (in seconds):", time_sec)

# time.strptime() method parse 
# a string representing a time
# according to the given format
# and returns a time.struct_time object

# Time string 
t = "14 Sep 2019 10:50:00"

# Parse the time string using
# time.strptime() method
obj2 = time.strptime(t, "% d % b % Y % H:% M:% S")

# Convert the time.struct_time
# object to local time expressed in
# seconds since the epoch
# using time.mktime() method
time_sec = time.mktime(obj2)

# Print the local time in seconds
print("\nLocal time (in seconds):", time_sec)
```

**Output:**

```
time.struct_time(tm_year=1970, tm_mon=1, tm_mday=12, tm_hour=13, tm_min=46,
tm_sec=40, tm_wday=0, tm_yday=12, tm_isdst=0)

Local time (in seconds): 980200.0

Local time (in seconds): 1568438400.0

```

**代码#2:** 如果参数是元组

```
# Python program to explain time.mktime() method 

# importing time module 
import time 

# A tuple containing 9 elements
# corresponding to time.struct_time object
# for example: consider the below object
# time.struct_time(tm_year = 2019, tm_mon = 9, tm_mday = 13, 
# tm_hour = 1, tm_min = 30, tm_sec = 26, tm_wday = 4,
# tm_yday = 256, tm_isdst = 0)

# Tuple corresponding to above 
# time.struct_time object will be
tup = (2019, 9, 13, 1, 30, 26, 4, 256, 0)

# Convert the above specified tuple
# to local time expressed in seconds
# since the epoch 
# using time.mktime() method
time_sec = time.mktime(tup)

# Print the time
print("Local Time (in seconds since the epoch):", time_sec)
```

**Output:**

```
Local Time (in seconds since the epoch): 1568318426.0

```

**代码#3:** 显示`***time.mktime()***`方法是`***time.localtime()***`方法的反函数

```
# Python program to explain time.mktime() method 

# importing time module 
import time 

# Get the current time
# expressed in seconds 
# since the epoch using
# time.time() method
curr_time = time.time() 

# Print the value
# returned by time.time() method
print("Current time (in seconds since the epoch):", curr_time)

# Convert the time expressed in seconds
# since the epoch to
# a time.struct_time object
# in local time using
# time.localtime() method 
obj = time.localtime(curr_time)

# Print the time.struct_time object
print("\ntime.struct_time object:")
print(obj, "\n")

# Convert the time.struct_time object
# back to the time expressed
# in seconds since the epoch
# in local time using
# time.mktime() method
time_sec = time.mktime(obj)

# Print the time
print("Time (in seconds since the epoch):", time_sec) 
```

**Output:**

```
Current time (in seconds since the epoch): 1568318426.2286296

time.struct_time object:
time.struct_time(tm_year=2019, tm_mon=9, tm_mday=13, tm_hour=1, tm_min=30,
tm_sec=26, tm_wday=4, tm_yday=256, tm_isdst=0) 

Time (in seconds since the epoch): 1568318426.0

```

**参考文献:**T2】https://docs.python.org/3/library/time.html#time.mktime