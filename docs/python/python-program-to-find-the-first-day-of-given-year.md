# Python 程序查找给定年份的第一天

> 原文:[https://www . geesforgeks . org/python-程序查找-给定年份的第一天/](https://www.geeksforgeeks.org/python-program-to-find-the-first-day-of-given-year/)

给定一年作为输入，编写一个 Python 来查找给定年份的开始日期。为了解决这个问题，我们将使用 Python 日期时间库。

**例:**

```py
Input : 2010
Output :Friday

Input :2019
Output :Tuesday

```

下面是实现:

```py
# Python program to find the first day of given year

# import datetime library
import datetime

def Startingday(year):

    # Creating an object for 1st January of that particular year
    # For that we are passing three argument (1) year (2) month
    # i.e 1 for january (3) date i.e 1 for starting day of 
    # that particular year
    a = datetime.datetime(year, 1, 1)

    # for printing Startingday of a particular year 
    # we are using a.strftime("% A")
    print("Starting day of year ", year, " is ", a.strftime("%A"))

# Driver Code
year = 2010
Startingday(year)
```

**输出:**

```py
Starting day of year  2010  is  Friday

```