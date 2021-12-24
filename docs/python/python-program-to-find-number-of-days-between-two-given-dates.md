# Python 程序查找两个给定日期之间的天数

> 原文:[https://www . geesforgeks . org/python-program-to-find-两个给定日期之间的天数/](https://www.geeksforgeeks.org/python-program-to-find-number-of-days-between-two-given-dates/)

给定两个日期，编写一个 Python 程序来计算它们之间的总天数。

**示例:**

```
Input : dt1 = 13/12/2018, dt2 = 25/2/2019
Output : 74 days

Input : dt1 = 01/01/2004, dt2 = 01/01/2005
Output : 366 days 
```

**天真的做法:**一个天真的解决方案是从 *dt1* 开始，一直数到 *dt2* 为止。此解决方案需要超过 O(1)的时间。

一个更好更简单的解决方案是从开始计算 dt1 前的总天数，即从 00/00/0000 到 *dt1* 的总天数，然后计算 *dt2* 前的总天数。最后，返回两个计数之间的差值。

## 蟒蛇 3

```
# Python3 program two find number of
# days between two given dates

# A date has day 'd', month 'm' and year 'y'

class Date:
    def __init__(self, d, m, y):
        self.d = d
        self.m = m
        self.y = y

# To store number of days in all months from
# January to Dec.
monthDays = [31, 28, 31, 30, 31, 30,
             31, 31, 30, 31, 30, 31]

# This function counts number of leap years
# before the given date

def countLeapYears(d):

    years = d.y

    # Check if the current year needs to be considered
    # for the count of leap years or not
    if (d.m <= 2):
        years -= 1

    # An year is a leap year if it is a multiple of 4,
    # multiple of 400 and not a multiple of 100.
    return int(years / 4) - int(years / 100) + int(years / 400)

# This function returns number of days between two
# given dates
def getDifference(dt1, dt2):

    # COUNT TOTAL NUMBER OF DAYS BEFORE FIRST DATE 'dt1'

    # initialize count using years and day
    n1 = dt1.y * 365 + dt1.d

    # Add days for months in given date
    for i in range(0, dt1.m - 1):
        n1 += monthDays[i]

    # Since every leap year is of 366 days,
    # Add a day for every leap year
    n1 += countLeapYears(dt1)

    # SIMILARLY, COUNT TOTAL NUMBER OF DAYS BEFORE 'dt2'

    n2 = dt2.y * 365 + dt2.d
    for i in range(0, dt2.m - 1):
        n2 += monthDays[i]
    n2 += countLeapYears(dt2)

    # return difference between two counts
    return (n2 - n1)

# Driver program
dt1 = Date(13, 12, 2018)
dt2 = Date(25, 2, 2019)

print(getDifference(dt1, dt2), "days")
```

**Output:** 

```
74 days
```

**使用 Python 日期时间模块:**

Python 自带一个内置的 *datetime* 模块，可以帮助我们解决各种与 datetime 相关的问题。为了找出两个日期之间的差异，我们只需输入带有日期类型的两个日期并减去它们，这又为我们提供了两个日期之间的天数。

## 蟒蛇 3

```
# Python3 program to find number of days
# between two given dates
from datetime import date

def numOfDays(date1, date2):
    return (date2-date1).days

# Driver program
date1 = date(2018, 12, 13)
date2 = date(2019, 2, 25)
print(numOfDays(date1, date2), "days")
```

**Output:** 

```
74 days
```