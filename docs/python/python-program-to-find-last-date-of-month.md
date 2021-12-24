# Python 程序查找本月最后一天

> 原文:[https://www . geeksforgeeks . org/python-程序查找-月末最后一天/](https://www.geeksforgeeks.org/python-program-to-find-last-date-of-month/)

给定一个日期时间对象，任务是编写一个 Python 程序来计算日期时间对象“月”的最后日期。

**示例:**

> **输入 ：** test_date = datetime.datetime（2018， 6， 4）
> 
> **输出:** 30
> 
> **说明:**每年 4 月有 30 天
> 
> **输入 ：** test_date = datetime.datetime（2020， 2， 4）
> 
> **输出:** 29
> 
> **说明:**2020 年 2 月有 29 天，闰年。

### **方法#1:使用 replace() + timedelta()**

在这种情况下，提取下个月，从下个月中减去提取的下个月对象的日期，得到下个月开始前的 1 天，即当月的最后一天。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Get Last date of Month
# Using replace() + timedelta()
import datetime

# initializing date
test_date = datetime.datetime(2018, 6, 4)

# printing original date
print("The original date is : " + str(test_date))

# getting next month
# using replace to get to last day + offset
# to reach next month
nxt_mnth = test_date.replace(day=28) + datetime.timedelta(days=4)

# subtracting the days from next month date to
# get last date of current Month
res = nxt_mnth - datetime.timedelta(days=nxt_mnth.day)

# printing result
print("Last date of month : " + str(res.day))
```

**输出:**

```
The original date is : 2018-06-04 00:00:00
Last date of month : 30
```

### **方法 2:使用日历()**

这使用内置函数来解决这个问题。在这种情况下，给定年份和月份，可以使用 monthrange()计算范围，其第二个元素可以获得所需的结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Get Last date of Month
# Using calendar()
from datetime import datetime
import calendar

# initializing date
test_date = datetime(2018, 6, 4)

# printing original date
print("The original date is : " + str(test_date))

# monthrange() gets the date range
# required of month
res = calendar.monthrange(test_date.year, test_date.month)[1]

# printing result
print("Last date of month : " + str(res))
```

**输出:**

```
The original date is : 2018-06-04 00:00:00
Last date of month : 30
```