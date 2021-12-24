# Python 程序查找给定日期的星期几

> 原文:[https://www . geeksforgeeks . org/python-程序查找给定日期的星期几/](https://www.geeksforgeeks.org/python-program-to-find-day-of-the-week-for-a-given-date/)

编写一个 Python 程序来查找过去或未来任何特定日期的星期几。让输入的格式为“年月日”。
**例:**

```py
Input : 03 02 1997 
Output : Monday

Input : 31 01 2019
Output : Thursday
```

已经讨论过的为给定日期寻找一周中某一天的方法是[天真方法](https://www.geeksforgeeks.org/find-day-of-the-week-for-a-given-date/)。现在，让我们来讨论一下 pythonic 方法。
**方法#1 :** 使用日期时间模块提供的 weekday()。
datetime 模块中 date 类的 weekday()函数，返回一周中某一天对应的整数。

## 蟒蛇 3

```py
# Python program to Find day of
# the week for a given date
import datetime
import calendar

def findDay(date):
    born = datetime.datetime.strptime(date, '%d %m %Y').weekday()
    return (calendar.day_name[born])

# Driver program
date = '03 02 2019'
print(findDay(date))
```

**Output:** 

```py
Sunday
```