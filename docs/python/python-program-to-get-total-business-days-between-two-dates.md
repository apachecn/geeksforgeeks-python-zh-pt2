# Python 程序获取两个日期之间的总工作日数

> 原文:[https://www . geesforgeks . org/python-program-to-get-两个日期之间的总工作日数/](https://www.geeksforgeeks.org/python-program-to-get-total-business-days-between-two-dates/)

给定两个日期，我们的任务是编写一个 Python 程序来获取总工作日，即两个日期之间的工作日。

**示例:**

> **输入:** test_date1，test_date2 = datetime(2015，6，3)，datetime(2015，7，1)
> 
> **输出:** 20
> 
> **说明:**工作日总计，即工作日跨度为 20 天。
> 
> **输入:** test_date1，test_date2 = datetime(2015，6，3)，datetime(2016，7，1)
> 
> **输出:** 282
> 
> **说明:**工作日总计，即工作日跨度为 282 天。

**方法 1:使用** [**时间增量()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/) **+** [**总和()**](https://www.geeksforgeeks.org/sum-function-python/) **+工作日()**

在这种情况下，所有日期都是使用 timedelta()通过增加差异直到结束日期来提取的。发布后，使用 weekday()过滤工作日，将所有小于 5 的值相加。即 Fri 周一。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Business days in range
# Using timedelta() + sum() + weekday()
from datetime import datetime, timedelta

# initializing dates ranges
test_date1, test_date2 = datetime(2015, 6, 3), datetime(2015, 7, 1)

# printing dates
print("The original range : " + str(test_date1) + " " + str(test_date2))

# generating dates
dates = (test_date1 + timedelta(idx + 1)
         for idx in range((test_date2 - test_date1).days))

# summing all weekdays
res = sum(1 for day in dates if day.weekday() < 5)

# printing
print("Total business days in range : " + str(res))
```

**输出:**

```py
The original range : 2015-06-03 00:00:00 2015-07-01 00:00:00
Total business days in range : 20
```

**方法 2:使用 np.busday_count()**

这是一个内置功能，可以直接用来解决这个任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Business days in range
# Using np.busday_count
from datetime import datetime, timedelta
import numpy as np

# initializing dates ranges 
test_date1, test_date2 = datetime(2015, 6, 3), datetime(2015, 7, 1)

# printing dates 
print("The original range : " + str(test_date1) + " " + str(test_date2))

# generating total days using busday_count()
res = np.busday_count(test_date1.strftime('%Y-%m-%d'),
                      test_date2.strftime('%Y-%m-%d'))

# printing 
print("Total business days in range : " + str(res))
```

**输出:**

```py
The original range : 2015-06-03 00:00:00 2015-07-01 00:00:00
Total business days in range : 20
```

**方法三:使用** [**熊猫. bdate_range()**](https://www.geeksforgeeks.org/pandas-bdate_range-function-in-python/)

这是另一个可以直接用来解决这个任务的内置功能。返回包括开始日期和结束日期在内的总业务日期列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Business days in range
# Using pd.bdate_range
from datetime import datetime
import pandas as pd

# initializing dates ranges
test_date1, test_date2 = datetime(2015, 6, 3), datetime(2015, 6, 30)

# printing dates
print("The original range : " + str(test_date1) + " " + str(test_date2))

# generating total days using pd.bdate_range()
# len() gets the number of days
# includes both last and first date.
res = len(pd.bdate_range(test_date1.strftime('%Y-%m-%d'),
                         test_date2.strftime('%Y-%m-%d')))

# printing result
print("Total business days in range : " + str(res))
```

**输出:**

```py
The original range : 2015-06-03 00:00:00 2015-06-30 00:00:00
Total business days in range : 20
```