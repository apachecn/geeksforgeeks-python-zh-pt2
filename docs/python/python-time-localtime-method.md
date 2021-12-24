# Python | time.localtime()方法

> 原文:[https://www.geeksforgeeks.org/python-time-localtime-method/](https://www.geeksforgeeks.org/python-time-localtime-method/)

**Python 中的时间模块**提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。
***Time . local Time()***方法**时间模块**用于将自纪元以来以秒为单位表示的时间转换为本地时间的***Time . struct _ Time***对象。
使用***time . gmtime()***方法将纪元后的给定时间(秒)转换为 UTC 中的***time . struct _ time***对象。
该方法返回一个带有命名元组接口的***time . struct _ time***对象。以下是***time . struct _ time***对象中的值:

<figure class="table">

| 索引 | 属性 | 价值观念 |
| **0** | **tm_year** | (例如，1993 年) |
| **1** | TM _ mon | 范围[1，12] |
| **2** | **tm_mday** | 范围[1，31] |
| **3** | **tm_hour** | 范围[0，23] |
| **4** | **tm_min** | 范围[0，59] |
| **5** | **tm_sec** | 范围[0，61] |
| **6** | **tm_wday** | 范围[0，6]，星期一是 0 |
| **7** | TM _ yday | 范围[1，366] |
| **8** | **tm_isdst** | 0、1 或-1 |
| **不适用** | **tm_zone** | 时区名称的缩写 |
| **不适用** | **tm_gmtoff** | 世界协调时以东的偏移量(秒) |

</figure>

> **语法:**time . local time([秒])
> **参数:**
> **(可选):表示时间的整数或浮点值，单位为秒。指定秒的分数将被忽略。如果未提供 secs 参数或无，则使用 time.time()方法返回的当前时间。
> **返回类型:**该方法返回类“time.struct_time”的对象。**

****代码#1:** 使用 ***time.localtime()*** 方法** 

## **蟒蛇 3**

```py
# Python program to explain time.localtime() method

# importing time module
import time

# If secs parameter
# is not given then
# the current time as
# returned by time.time() method
# is used

# Convert the current time in seconds
# since the epoch to a
# time.struct_time object in Local time
obj = time.localtime()

# Print the time.struct.time object
print(obj)

# We can change it to
# Day Mon date Hour:Min:Sec year
# format using time.asctime() method
t = time.asctime(obj)
print(t)
```

****Output:** 

```py
time.struct_time(tm_year=2019, tm_mon=8, tm_mday=22, tm_hour=10, tm_min=3,
tm_sec=15, tm_wday=3, tm_yday=234, tm_isdst=0)
Thu Aug 22 10:03:15 2019
```** 

****代码#2:** 使用 ***time.localtime()*** 方法** 

## **蟒蛇 3**

```py
# Python program to explain time.localtime() method

# importing time module
import time

# Time in seconds
# since the epoch
secs = 950000000

# Convert the given time in seconds
# since the epoch to a
# time.struct_time object in local time
# using time.localtime() method
obj = time.localtime(secs)

# Print the time.struct_time object
print("time.struct_time object for seconds =", secs)
print(obj)

# Time in seconds
# since the epoch
secs = 950000000.81956

# Convert the given time in seconds
# since the epoch to a
# time.struct_time object in local time
# using time.localtime() method
obj = time.localtime(secs)

# Print the time.struct_time object
print("\ntime.struct_time object for seconds =", secs)
print(obj)

# Output for secs = 950000000
# and secs = 950000000.81956
# will be same because
# fractions in 950000000.81956
# i.e .81956 will be ignored
```

****Output:** 

```py
time.struct_time object for seconds = 950000000
time.struct_time(tm_year=2000, tm_mon=2, tm_mday=8, tm_hour=14, tm_min=23,
tm_sec=20, tm_wday=1, tm_yday=39, tm_isdst=0)

time.struct_time object for seconds = 950000000.81956
time.struct_time(tm_year=2000, tm_mon=2, tm_mday=8, tm_hour=14, tm_min=23,
tm_sec=20, tm_wday=1, tm_yday=39, tm_isdst=0)
```** 

****参考:**T2https://docs.python.org/3/library/time.html#time.localtime**