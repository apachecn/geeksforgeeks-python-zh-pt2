# Python |打印给定年份列表中的闰年数

> 原文:[https://www . geesforgeks . org/python-print-给定年份列表中的闰年数/](https://www.geeksforgeeks.org/python-print-number-of-leap-years-from-given-list-of-years/)

查找闰年的问题非常普遍，我们可能会面临在给定的年份列表中查找闰年数的问题。让我们讨论一下实现这一点的某些方法。

**方法#1:使用迭代**
检查年是 4 的倍数而不是 100 的倍数还是年是 400 的倍数。

## 蟒蛇 3

```
# Python code to finding number of
# leap years in list of years.

# Input list initialization
Input = [2001, 2002, 2003, 2004, 2005, 2006,
         2007, 2008, 2009, 2010, 2011, 2012]

# Find whether it is leap year or not
def checkYear(year):
    return (((year % 4 == 0) and
             (year % 100 != 0)) or
             (year % 400 == 0))

# Answer Initialization
Answer = 0

for elem in Input:
    if checkYear(elem):
        Answer = Answer + 1

# Printing
print("No of leap years are:", Answer)
```

**Output:** 

```
No of leap years are: 3
```

**方法 2:使用日历**

## 蟒蛇 3

```
# Python code to finding number of
# leap years in list of years.

# Importing calendar
import calendar

# Input list initialization
Input = [2001, 2002, 2003, 2004, 2005,
         2006, 2007, 2008, 2009, 2010]

# Using calendar to find leap year
def FindLeapYear(Input):
    ans = 0
    for elem in Input:
        if calendar.isleap(int(elem)):
            ans = ans + 1
    return ans

Output = FindLeapYear(Input)

# Printing
print("No of leap years are:", Output)
```

**Output:** 

```
No of leap years are: 2
```