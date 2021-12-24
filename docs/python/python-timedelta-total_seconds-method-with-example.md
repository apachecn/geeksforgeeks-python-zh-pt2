# Python 时间增量 total_seconds()方法示例

> 原文:[https://www . geesforgeks . org/python-time delta-total _ seconds-method-with-example/](https://www.geeksforgeeks.org/python-timedelta-total_seconds-method-with-example/)

**total_seconds()** 函数用于返回指定持续时间实例覆盖的总秒数。该函数用于模块 DateTime 的 timedelta 类。

> **语法:** total_seconds()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回指定持续时间实例覆盖的总秒数。

**示例 1:** 在下面的示例中，在 total_seconds()函数的帮助下，将以第二个值的形式返回 55 分钟。

## 蟒蛇 3

```
# Python3 code for getting
# total seconds for the
# given duration of time

# Importing time and timedelta module
from datetime import time, timedelta 

# Specifying a time duration
A = timedelta(minutes = 55)

# Calling the total_seconds() function
# over the specified time duration
totalsecond = A.total_seconds()

# Getting the Total seconds for
# the duration of 55 minutes
print("Total seconds in 55 minutes:", totalsecond)
```

**输出:**

```
Total seconds in 55 minutes: 3300.0
```

**示例 2:** 在下面的示例中，借助 total_seconds()函数，将根据第二个值返回-3*13 分钟。

## 蟒蛇 3

```
# Python3 code for getting
# total seconds for the
# given duration of time

# Importing time and timedelta module
from datetime import time, timedelta 

# Specifying a time duration
A = timedelta(minutes = -3*13)

# Calling the total_seconds() function
# over the specified time duration
totalsecond = A.total_seconds()

# Getting the Total seconds for
# the duration of -3*13 minutes
print("Total seconds in -3*13 minutes:", totalsecond)
```

**输出:**

```
Total seconds in -3*13 minutes: -2340.0
```

**示例 3:** 在下面的示例中，total_seconds()函数正在将“天= 2，小时= 3，分钟= 43，秒= 35”的持续时间转换为其等效的秒值。

## 蟒蛇 3

```
# Python3 code for getting
# total seconds for the
# given duration of time

# Importing time and timedelta module
from datetime import time, timedelta 

# Specifying a time duration
A = timedelta(days = 2, hours = 3,
              minutes = 43,
              seconds = 35)

# Calling the total_seconds() function
# over the specified time duration
totalsecond = A.total_seconds()

# Getting the Total seconds
print("Total seconds are:", totalsecond)
```

**输出:**

```
Total seconds are: 186215.0
```