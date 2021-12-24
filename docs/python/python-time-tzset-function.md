# Python time.tzset()函数

> 原文:[https://www.geeksforgeeks.org/python-time-tzset-function/](https://www.geeksforgeeks.org/python-time-tzset-function/)

在 Python 中，时间模块的 tzset()函数基于使用环境变量 TZ 的重新初始化设置。python 中时间模块的 tzset()方法重置时间转换协议。该时区表示世界协调时以西的非夏令时秒，而备用时区表示世界协调时以西的夏令时秒。TZ 环境变量的常规形式是:

```
std offset [dst [offset [,start[/time], end[/time]]]]
```

其中组件是:

*   **std 和 dst:** 是由三个或更多字母数字值给出的时区收缩。这些将分散到 python 中的 tzname()时间函数中。
*   **偏移量:**在 tzset()，中，偏移量的形式为:hh[:mm[:ss]]。这表示到达世界协调时的当地时间的增值。如果前面有一个“-”号，时区在本初子午线以东。否则，它就是西方。如果夏令时之后没有偏移，则假设夏令时比标准时间早一小时。
*   **开始[/时间]，结束[/时间]:** 显示何时切换到夏令时以及何时从夏令时切换回来。开始和结束日期遵循以下格式之一:
*   **Jn:** 儒略日 n，其中 n 在 1 到 365 的范围内(1 < = n < = 365)。在这种情况下，我们不计算闰日，所以在所有年份中，2 月 28 日是第 59 天，3 月 1 日是第 60 天。
*   **n:** 从零开始的儒略日(0 < = n < = 365)，范围为 0 到 365。在这种情况下，我们计算闰日，有可能指向 2 月 29 日。
*   **Mm.n.d:** 一年 m 月 n 周的第 d 天(0<= d<= 6)(1<= n<= 5，1 < = m < = 12，其中第 5 周表示“m 月的最后 d 天”，可能发生在第四周或第五周)。第一周是 d 日发生的第一周。第零天是星期天。
*   **时间:**这遵循与 offset 相同的格式，除了前导符号(“-”或“+”)不允许出现在这里。如果没有给出默认时间，则默认时间为 02:00:00。

**语法:**

```
time.tzset()
```

**参数:**

钠

**返回值:**

不返回值。

**注意**:虽然在很多情况下，如果我们改变 TZ 环境变量，可能会影响 localtime()之类的函数的输出，但不需要调用 tzset()，这种行为是不应该依赖的。TZ 环境变量不应包含空格。

**例 1** :

## 蟒蛇 3

```
# time.tzset() Function in python

# importin time and os module
import time
import os

# Define TZ environment variable
os.environ['TZ'] = 'EST+05EDT,M4.1.0,M10.5.0'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))

# Define TZ environment variable again
os.environ['TZ'] = 'AEST-10AEDT-11,M10.5.0,M3.5.0'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))
```

**Output**

```
08:47:24 11/19/21 EST
00:47:24 11/20/21 AEDT
```

**例 2:**

## 蟒蛇 3

```
# time.tzset() Function in python

# importin time and os module
import time
import os

# Define TZ environment variable
os.environ['TZ'] = 'UTC'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))

# Define TZ environment variable again
os.environ['TZ'] = 'Europe/Amsterdam'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))
```

**Output**

```
12:14:00 11/23/21 UTC
13:14:00 11/23/21 CET
```

**例 3:**

## 蟒蛇 3

```
# time.tzset() Function in python

# importin time and os module
import time
import os

# Define TZ environment variable
os.environ['TZ'] = 'Australia/Melbourne'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))

# Define TZ environment variable again
os.environ['TZ'] = 'Egypt'

# reset the time conversion rules
time.tzset()

# print time
print(time.strftime('%X %x %Z'))
```

**Output**

```
23:14:00 11/23/21 AEDT
14:14:00 11/23/21 EET
```