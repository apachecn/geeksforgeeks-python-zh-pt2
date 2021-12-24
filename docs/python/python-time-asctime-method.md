# Python | time.asctime()方法

> 原文:[https://www.geeksforgeeks.org/python-time-asctime-method/](https://www.geeksforgeeks.org/python-time-asctime-method/)

**Python time 方法 time . as time()**用于将元组或 **time.struct_time** 对象转换为以下形式的字符串，该对象表示由 **time.gmtime()** 或 **time.localtime()** 方法返回的时间:

```py
Day Mon Date Hour:Min:Sec Year
For example:
Thu 08 22 10:46:56 2019
```

### Python 时间 asctime()语法:

> time.asctime（[t]）

### Python time as time()**参数:**

> **t** (可选):一个元组或 time.struct_time 对象，表示 time.gmtime()或 time.localtime()方法返回的时间。如果未提供“t”参数或“无”，则使用 time.localtime()方法返回的当前时间。

### Python time as time()**返回类型:**

> 该方法返回一个形式为**日周一日期小时:分钟:秒年**的字符串

## Python 时间示例 asctime()

### 示例 1:time . as time()方法的使用

## 蟒蛇 3

```py
# Python program to explain time.asctime() method

# importing time module
import time

# Convert the current time
# as returned by time.time() method
# to a time.struct_time object in UTC
# using time.gmtime() method
obj = time.gmtime()

# Print time.struct_time object
print("time.struct_time object as returned by time.gmtime() method:")
print(obj)

# Convert the time.struct_time
# object to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime(obj)

# Print the time.struct_time object
# to the string of the
# form 'Day Mon Date Hour:Min:Sec Year'
print("\ntime.struct_time obj in string of the form \
'Day Mon Date Hour:Min:Sec Year':")
print(time_str)

# Convert the current time
# as returned by time.time() method
# to a time.struct_time object in local time
# using time.localtime() method
obj = time.localtime()

# Print time.struct_time object
print("\ntime.struct_time object as returned by \
time.localtime() method:")
print(obj)

# Convert the time.struct_time
# object to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime(obj)

# Print the time.struct_time object
# to the string of the
# form 'Day Mon Date Hour:Min:Sec Year'
print("\ntime.struct_time obj in string of the form \
'Day Mon Date Hour:Min:Sec Year':")
print(time_str)
```

**输出:**

> time.struct_time 对象，由 time.gmtime()方法返回:
> 
> time.struct_time(tm_year=2021，tm_mon=10，tm_mday=7，tm_hour=15，tm_min=30，tm_sec=51，tm_wday=3，tm_yday=280，tm_isdst=0)
> 
> “日周一日期小时:分钟:秒年”形式的 time.struct_time 对象:
> 
> 2021 年 10 月 7 日星期四 15:30:51
> 
> time.struct_time 对象由 time.localtime()方法返回:
> 
> time.struct_time(tm_year=2021，tm_mon=10，tm_mday=7，tm_hour=21，tm_min=0，tm_sec=51，tm_wday=3，tm_yday=280，tm_isdst=0)
> 
> “日周一日期小时:分钟:秒年”形式的 time.struct_time 对象:
> 
> 2021 年 10 月 7 日星期四 21:00:51

### **例 2:** 如果未提供参数‘t’

## 蟒蛇 3

```py
# Python program to explain time.asctime() method

# importing time module
import time

# If the parameter 't'
# in time.asctime() method
# is not provided then
# the current time as
# returned by time.localtime()
# method is used

# Convert the current time
# as returned by time.localtime() method
# to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime()

# Print the string
print(time_str)
```

**输出:**

```py
Thu Oct  7 21:01:45 2021
```

### **示例 3:** 如果参数‘t’是元组

## 蟒蛇 3

```py
# Python program to explain time.asctime() method

# importing time module
import time

# A tuple with 9 attributes
# representing a time
t = (2019, 8, 22, 11, 21, 48, 3, 234, 0)

# Convert the tuple
# to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime(t)

# Print the string
print(time_str)
```

**输出:**

```py
Thu Aug 22 11:21:48 2019
```