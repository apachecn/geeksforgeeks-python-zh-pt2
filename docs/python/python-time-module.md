# Python 时间模块

> 原文:[https://www.geeksforgeeks.org/python-time-module/](https://www.geeksforgeeks.org/python-time-module/)

在本文中，我们将借助好的例子讨论时间模块和该模块提供的各种功能。

顾名思义，Python 时间模块允许在 Python 中使用时间。它允许获得当前时间、暂停程序执行等功能。所以在开始这个模块之前，我们需要导入它。

## 导入时间模块

时间模块自带 Python 的标准实用程序模块，无需外部安装。我们可以简单的使用[导入语句](https://www.geeksforgeeks.org/import-module-python/)导入。

```py
import time
```

## 什么是纪元？

纪元是时间开始的点，并且依赖于平台。在 Windows 和大多数 Unix 系统上，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)，闰秒不会计入自纪元以来的秒数。要检查给定平台上的纪元是什么，我们可以使用 [time.gmtime(0)](https://www.geeksforgeeks.org/python-time-gmtime-method/) 。

**示例:**获取纪元

## 蟒蛇 3

```py
import time

print(time.gmtime(0))
```

**输出:**

> time.struct_time(tm_year=1970，tm_mon=1，tm_mday=1，tm_hour=0，tm_min=0，tm_sec=0，tm_wday=3，tm_yday=1，tm_isdst=0)

从上面的例子中，你可以看到纪元是 1970 年 1 月 1 日。这意味着 1970 年 1 月 2 日可以表示为自纪元以来的 86400 秒，因为一天中有 86400 秒。

**注意:**历元之前的时间仍然可以用秒来表示，但会是负数。例如，1969 年 12 月 31 日将表示为-86400 秒。

获取自纪元以来的当前时间(秒)

[time.time()](https://www.geeksforgeeks.org/python-time-time-method/) 方法返回自纪元以来的当前时间，单位为秒。它返回一个浮点数。

**示例:**自纪元以来的当前时间(秒)

## 蟒蛇 3

```py
import time

curr = time.time()
print("Current time in seconds since epoch =", curr)
```

**Output**

```py
Current time in seconds since epoch = 1627908387.764925
```

## 从秒获取时间字符串

[time.ctime()](https://www.geeksforgeeks.org/python-time-ctime-method/) 函数返回一个 24 个字符的时间字符串，但以秒为参数，计算到上述秒的时间。如果没有争论通过，时间被计算到现在。

**示例:**从秒获取时间字符串

## 蟒蛇 3

```py
import time

# getting current time by passing
# the number of seconds since epoch
curr = time.ctime(1627908313.717886)
print("Current time:", curr)
```

**Output**

```py
Current time: Mon Aug  2 12:45:13 2021
```

## 延迟程序的执行

使用 [time.sleep()](https://www.geeksforgeeks.org/sleep-in-python/) 方法可以延迟执行。此方法用于在参数中指定的时间内暂停程序执行。

**示例:**延迟 Python 中程序的执行时间。

## 蟒蛇 3

```py
import time

for i in range(4):

    # using sleep() to hault execution
    time.sleep(1)
    print(i)
```

**Output**

```py
0
1
2
3
```

## 时间结构时间类

Struct_time 类有助于访问本地时间，即非划时代的时间戳。它返回一个命名元组，其值可以通过索引和属性名来访问。其对象包含以下属性–

<figure class="table">

| 索引 | 属性名 | 价值观念 |
| --- | --- | --- |
| Zero | tm _ 年 | 0000, …, 9999 |
| one | tm_mon(消歧义) | 1, 2, …, 11, 12 |
| Two | tm_mday | 1, 2, …, 30, 31 |
| three | tm _ 小时 | 0, 1, …, 22, 23 |
| four | tm_min | 0, 1, …, 58, 59 |
| five | tm_sec | 0, 1, …, 60, 61 |
| six | tm_wday | 0, 1, …, 6;星期天是 6 点 |
| seven | tm_yday | 1, 2, …, 365, 366 |
| eight | tm_isdst | 0、1 或-1 |

</figure>

这个类包含各种函数。让我们详细讨论每个函数。

## time.localtime()方法

[localtime()](https://www.geeksforgeeks.org/python-time-localtime-method/) 方法返回本地时间中的 struct_time 对象。它以自 epoch 以来经过的秒数作为参数。如果没有给出秒参数，则使用 time.time()方法返回的当前时间。

**示例:**从纪元获取本地时间

## 蟒蛇 3

```py
# importing time module
import time

# Convert the current time in seconds
# since the epoch to a
# time.struct_time object in Local time
obj = time.localtime(1627987508.6496193)

print(obj)
```

**输出**

> time.struct_time(tm_year=2021，tm_mon=8，tm_mday=3，tm_hour=16，tm_min=15，tm_sec=8，tm_wday=1，tm_yday=215，tm_isdst=0)

## time.mktime()方法

[time.mktime()](https://www.geeksforgeeks.org/python-time-mktime-method/) 是 time.localtime()的反函数，它将自纪元以来以秒为单位表示的时间转换为以本地时间表示的 time.struct_time 对象。

**示例:**将 struct_time 对象转换为自纪元以来的秒数

## 蟒蛇 3

```py
# importing time module
import time

obj1 = time.gmtime(1627987508.6496193)

# Convert the time.struct_time
# object to local time expressed in
# seconds since the epoch
# using time.mktime() method
time_sec = time.mktime(obj1)

# Print the local time in seconds
print("Local time (in seconds):", time_sec)
```

**Output**

```py
Local time (in seconds): 1627987508.0
```

## time.gmtime()方法

[time.gmtime()](https://www.geeksforgeeks.org/python-time-gmtime-method/) 用于将自纪元以来以秒为单位表示的时间转换为 UTC 中的 time.struct_time 对象，其中 tm_isdst 属性始终为 0。如果没有给出秒参数，则使用 time.time()方法返回的当前时间。

**示例:**time . gmtime()方法的使用

## 蟒蛇 3

```py
# importing time module
import time

# Convert the current time in seconds
# since the epoch to a
# time.struct_time object in UTC
obj = time.gmtime(1627987508.6496193)

# Print the time.struct.time object
print(obj)
```

**输出**

> time.struct_time(tm_year=2021，tm_mon=8，tm_mday=3，tm_hour=10，tm_min=45，tm_sec=8，tm_wday=1，tm_yday=215，tm_isdst=0)

## time.strftime()方法

[time.strftime()](https://www.geeksforgeeks.org/time-strftime-function-in-python/) 函数将表示由 gmtime()或 localtime()返回的时间的元组或 struct_time 转换为由 format 参数指定的字符串。如果未提供 t，则使用 localtime()返回的当前时间。格式必须是字符串。如果 t 中的任何字段超出允许的范围，将引发 ValueError。

**示例:**使用 strftime()方法将 struct_time 对象转换为字符串

## 蟒蛇 3

```py
from time import gmtime, strftime

# using simple format of showing time
s = strftime("%a, %d %b %Y %H:%M:%S",
             gmtime(1627987508.6496193))
print(s)
```

**Output**

```py
Tue, 03 Aug 2021 10:45:08
```

## time . as time()方法

[time . as time()](https://www.geeksforgeeks.org/python-time-asctime-method/)方法用于将 time.gmtime()或 time.localtime()方法返回的表示时间的元组或 time.struct_time 对象转换为以下形式的字符串:

```py
Day Mon Date Hour:Min:Sec Year
```

**示例:**将元组转换为时间。将 struct_time 对象转换为字符串

## 蟒蛇 3

```py
# importing time module
import time

obj = time.gmtime(1627987508.6496193)

# Convert the time.struct_time
# object to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime(obj)
print(time_str)

obj = time.localtime(1627987508.6496193)

# Convert the time.struct_time
# object to a string of the
# form 'Day Mon Date Hour:Min:Sec Year'
# using time.asctime() method
time_str = time.asctime(obj)
print(time_str)
```

**Output**

```py
Tue Aug  3 10:45:08 2021
Tue Aug  3 10:45:08 2021
```

## time.strptime()方法

方法将表示时间的字符串转换为 struct_time 对象。

**示例:**将字符串转换为 struct_time 对象。

## 蟒蛇 3

```py
import time

string = "Tue, 03 Aug 2021 10:45:08"
obj = time.strptime(string, "%a, %d %b %Y %H:%M:%S")

print(obj)
```

**输出**

> time.struct_time(tm_year=2021，tm_mon=8，tm_mday=3，tm_hour=10，tm_min=45，tm_sec=8，tm_wday=1，tm_yday=215，tm_isdst=-1)