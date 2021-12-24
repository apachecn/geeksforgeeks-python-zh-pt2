# Python 中 Datetime.date 类的常规()函数

> 原文:[https://www . geesforgeks . org/toordinal-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/toordinal-function-of-datetime-date-class-in-python/)

**toordinal()** 函数用于返回指定日期时间实例的前序公历序数。

**注:**公历序数给出了从 01/0001 年 1 月 1 日算起的天数。这里序数被称为序言，因为公历本身是从 1582 年 10 月开始的。

> **语法:** toordinal()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回日期时间实例的前序公历序数。

**例 1:** 使用今天的日期。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting the proleptic Gregorian
# ordinal of a datetime instance

# importing datetime and time module
import datetime
import time

# Getting today's date
todays_Date = datetime.date.fromtimestamp(time.time());

# Calling the toordinal() function over the
# today's date
date = todays_Date.toordinal();

# Printing the proleptic Gregorian ordinal
# for the today's date
print("Proleptic Ordinal for today's date: %s"%date);
```

**输出:**

```
Proleptic Ordinal for today's date: 737998
```

**例 2:** 使用今天的日期和时间。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting the proleptic Gregorian
# ordinal of a datetime instance

# importing datetime and time module
import datetime
import time

# Getting today's date and time
todays_DateTime = datetime.datetime.now();

# Calling the toordinal() function over the
# today's date and time
DateTime = todays_DateTime.toordinal();

# Printing the proleptic Gregorian ordinal
# for the today's date and time
print("Proleptic Ordinal for today's date and time: %s"%DateTime);
```

**输出:**

```
Proleptic Ordinal for today's date and time: 737998
```

**示例 3:** 使用特定日期。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting the proleptic Gregorian
# ordinal of a datetime instance

# importing datetime and time module
import datetime
import time

# Initializing a date and time
DateTime = datetime.datetime(1358, 8, 12, 1, 3, 4, 9);

# Calling the toordinal() function over the
# above date and time
Date_Time = DateTime.toordinal();

# Printing the proleptic Gregorian ordinal
# for the above given date and time
print("Proleptic Ordinal for today's date and time: %s"%Date_Time);
```

**输出:**

```
Proleptic Ordinal for today's date and time: 495858
```