# Python 程序打印有效的递增日期

> 原文:[https://www . geesforgeks . org/python-program-to-print-递增日期-如果有效/](https://www.geeksforgeeks.org/python-program-to-print-the-incremented-date-if-valid/)

在本文中，我们将编写一个 python 程序来输入日期，并检查它是否是有效的日期。如果有效，输出递增的日期。否则，打印“无效日期”。

**示例:**

```py
Input : 1/2/2000
Output: 2/2/2000

Input : 29/2/2002
Output: Invalid date

Input : 31/12/2015
Output: 1/1/2016 
```

第一步是检查输入的日期是否有效。对于这一步，我们需要首先获取输入月份的最大可能天数。然后我们需要看看日期是否在 1 和获得的最大天数之间，月份是否在 1 和 12 之间。如果这两个条件都得到满足，这意味着它是一个有效的日期，我们需要增加它。为了增加日期，我们需要处理以下情况:

1.  如果输入的日期是一年的最后一天。
2.  如果输入的日期是一个月的最后一天。
3.  如果输入的日期不是一个月的最后一天。

对于第一种情况，递增年份并将日期和月份都设置为 1。对于第二种情况，增加月份并将日期设置为 1。对于第三种情况，只需增加一天。如果两个条件中甚至有一个没有得到满足，那么它就是无效日期。

下面是实现。

## 蟒蛇 3

```py
# input the date and split it to day, month and year
day, month, year = map(int, input().split('/'))

if month == 2:

    # check for February
    if year % 4 != 0:
        d_max = 28
    else:
        d_max = 29

elif month in [4, 6, 9, 11]:

    # check the months with 30 days
    d_max = 30

else:
    d_max = 31

if 1 <= day <= d_max and 1 <= month <= 12:

    # increment the date since it is a
    # valid date
    if day == d_max:
        day = 1
        if month == 12:

            # If this block is entered,
            # then it is the last day of
            # the year
            month = 1
            year += 1
        else:

            # If this block is entered,
            # then it is the last day of
            # the month
            month += 1
    else:

        # If this block is entered, then it
        # is NOT the last day of the month
        day += 1
    print(str(day) + "/" + str(month) + "/" + str(year))
else:
    print("Invalid date")
```

**输出:**

```py
31/12/2015
1/1/2016
```