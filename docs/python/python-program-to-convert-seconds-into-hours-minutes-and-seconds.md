# Python 程序将秒转换为小时、分钟和秒

> 原文:[https://www . geesforgeks . org/python-程序-将秒转换为小时-分-秒/](https://www.geeksforgeeks.org/python-program-to-convert-seconds-into-hours-minutes-and-seconds/)

给定一个整数 *n* (以秒为单位)，将其转换为小时、分钟和秒。

**示例:**

```
Input : 12345
Output : 3:25:45

Input : 3600
Output : 1:00:00

```

**方法#1 :** 幼稚

这种方法只是一种通过简单的数学计算来获得小时、分钟和秒的幼稚方法。

```
# Python Program to Convert seconds
# into hours, minutes and seconds

def convert(seconds):
    seconds = seconds % (24 * 3600)
    hour = seconds // 3600
    seconds %= 3600
    minutes = seconds // 60
    seconds %= 60

    return "%d:%02d:%02d" % (hour, minutes, seconds)

# Driver program
n = 12345
print(convert(n))
```

**Output:**

```
3:25:45

```

**方法#2 :** 替代天真方法

通过使用`divmod()`函数，它只进行一次除法来产生商和余数，只需两次数学运算，就可以很快得到结果。

```
# Python Program to Convert seconds
# into hours, minutes and seconds

def convert(seconds):
    min, sec = divmod(seconds, 60)
    hour, min = divmod(min, 60)
    return "%d:%02d:%02d" % (hour, min, sec)

# Driver program
n = 12345
print(convert(n))
```

**Output:**

```
3:25:45

```

**方法 3 :** 使用`timedelta`(模块`datetime`的对象)

日期时间模块提供*时间增量*对象，该对象表示一个持续时间，即两个日期或时间之间的差值。`datetime.timedelta`可以用秒表示成小时、分钟和秒的格式。

```
# Python Program to Convert seconds
# into hours, minutes and seconds
import datetime

def convert(n):
    return str(datetime.timedelta(seconds = n))

# Driver program
n = 12345
print(convert(n))
```

**Output:**

```
3:25:45

```

**使用`time.strftime()`接近#4 :**

`time.strftime()`对格式进行更多控制。格式和`time.gmtime()`作为参数传递。 *gmtime* 用于将秒转换为`strftime()`要求的特殊元组格式。

```
# Python Program to Convert seconds
# into hours, minutes and seconds

import time

def convert(seconds):
    return time.strftime("%H:%M:%S", time.gmtime(n))

# Driver program
n = 12345
print(convert(n))
```

**Output:**

```
03:25:45

```