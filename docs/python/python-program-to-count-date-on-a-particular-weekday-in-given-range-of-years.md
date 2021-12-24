# Python 程序，用于计算给定年份范围内特定工作日的日期

> 原文:[https://www . geeksforgeeks . org/python-在给定的年份范围内的特定工作日计算程序日期/](https://www.geeksforgeeks.org/python-program-to-count-date-on-a-particular-weekday-in-given-range-of-years/)

给定一个日期，我们的任务是获取工作日索引和年范围，计算日期在年范围内特定工作日的总出现次数。

**示例:**

> **输入:**日期= 13，周= 5，strt，结束= 1950，2020
> 
> **输出:** 120
> 
> **说明:**从 1950 年到 2020 年，星期五 13 的总日期是 120。
> 
> **输入:**日期= 13，周= 1，strt，结束= 1950，2050
> 
> **输出:** 173
> 
> **说明:**从 1950 年到 2050 年，13 号星期一的总日期是 173。

**方法一:使用** [**循环**](https://www.geeksforgeeks.org/understanding-for-loop-in-python/) **+工作日()**

在这种情况下，我们运行一个嵌套循环，从开始的一年到结束的一年，在每一年中，每个月都用一个日期进行检查，如果找到，计数器就会递增。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Count date on weekday in Year Range
# Using loop + weekday()
from datetime import datetime

# initializing date
date = 13

# initializing weekday
weekdy = 5

# initializing range of Years
strt, end = 1950, 2020

# printing Number
print("The date, weekday : " + str(date) + " " + str(weekdy))

res = 0
for year in range(strt, end + 1):

    # checking each month for same date
    # weekday combination
    for month in range(1, 13):
        if datetime(year, month, date).weekday() == weekdy:
            res += 1

# printing result
print("Total dates with same weekday : " + str(res))
```

**输出:**

```py
The date, weekday : 13 5
Total dates with same weekday : 120
```

**方法二:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+** [**发生器表达式**](https://www.geeksforgeeks.org/generator-expressions/)

与上述方法类似，唯一的区别是生成器表达式用于嵌套循环的任务，sum()执行对找到的正确年、月组合求和的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Count date on weekday in Year Range
# Using sum() + generator expression
from datetime import datetime

# initializing date
date = 13

# initializing weekday
weekdy = 5

# initializing range of Years
strt, end = 1950, 2020

# printing Number
print("The date, weekday : " + str(date) + " " + str(weekdy))

# sum performs accumulation
res = sum(datetime(year, month, date).weekday() == weekdy
          for year in range(strt, end + 1) for month in range(1, 13))

# printing result
print("Total dates with same weekday : " + str(res))
```

**输出:**

```py
The date, weekday : 13 5
Total dates with same weekday : 120
```