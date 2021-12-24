# Python |以字符串形式给出的日期排序列表

> 原文:[https://www . geesforgeks . org/python-sort-list-date-以字符串形式给出/](https://www.geeksforgeeks.org/python-sort-list-of-dates-given-as-strings/)

给定一个字符串格式的日期列表，编写一个 Python 程序以升序对日期列表进行排序。

**示例:**

> **输入:**日期=[“2017 年 7 月 24 日”、“2017 年 7 月 25 日”、“1996 年 6 月 11 日”、“2019 年 1 月 01 日”、“2005 年 8 月 12 日”、“1997 年 1 月 01 日”]
> 
> **输出:【2007 年 1 月 1 日【2016 年 7 月 10 日【2017 年 12 月 2 日
> 2018 年 6 月 11 日
> 2018 年 6 月 23 日
> 2019 年 1 月 1 日**

**方法:**
在 Python 中，我们可以使用`sort()`(用于就地排序)和`sorted()`(返回新的排序列表)函数对列表进行排序。但是默认情况下，这些内置的排序函数将按字母顺序对字符串列表进行排序，这在我们的例子中会导致错误的顺序。因此，我们需要传递一个`key`参数来告诉排序函数，我们需要以一种特定的方式比较列表项，并对它们进行相应的排序。

在 Python 中，我们有`datetime`模块，这使得基于日期的比较更加容易。`datetime.strptime()`函数用于将给定的字符串转换为日期时间对象。它接受两个参数:*日期*(字符串)和*格式*(用于指定格式。for eg: %Y 用于指定年份)并返回一个 datetime 对象。

**语法:**

```
datetime.strptime(date, format)
```

解决此问题所需的格式如下:

```
%d ---> for Day
%b ---> for Month
%Y ---> for Year

```

因此，我们需要在排序函数中传递`datetime` 对象作为`key`参数，以告诉排序函数它需要通过将字符串转换为日期来比较字符串，并以递增的顺序对它们进行排序。

下面是上述方法的实现:

```
# Python3 program to sort the list of dates
# given in string format

# Import the datetime module
from datetime import datetime

# Function to print the data stored in the list 
def printDates(dates): 

    for i in range(len(dates)):  
        print(dates[i]) 

if __name__ == "__main__":  

    dates =  ["23 Jun 2018", "2 Dec 2017", "11 Jun 2018", 
              "01 Jan 2019", "10 Jul 2016", "01 Jan 2007"]  

    # Sort the list in ascending order of dates 
    dates.sort(key = lambda date: datetime.strptime(date, '%d %b %Y'))

    # Print the dates in a sorted order 
    printDates(dates) 
```

**Output:**

```
01 Jan 2007
10 Jul 2016
2 Dec 2017
11 Jun 2018
23 Jun 2018
01 Jan 2019

```