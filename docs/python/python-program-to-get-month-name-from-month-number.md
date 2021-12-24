# Python 程序从月号

中获取月名

> 原文:[https://www . geesforgeks . org/python-程序-月-月-名-月-号/](https://www.geeksforgeeks.org/python-program-to-get-month-name-from-month-number/)

给定一个日期时间对象或月号，任务是编写一个 Python 程序，从中获取相应的月名。

**示例:**

> **输入:** test_date = datetime(2020，4，8)
> 
> **输出:**4 月
> 
> **说明:**第 4 个月是 4 月。
> 
> **输入:** test_date = datetime(2020，1，8)
> 
> **产量:**1 月
> 
> **说明:**1 月为 1 月。

### **方法#1:使用**[**str time()**](https://www.geeksforgeeks.org/python-strftime-function/)**+% B**

在本例中，我们使用 strftime()将日期对象转换为格式字符串，并通过提供%B，强制返回一个月名。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get Month Name from Month Number
# Using strftime() + %B
from datetime import datetime

# initializing date
test_date = datetime(2020, 4, 8)

# printing original date
print("The original date is : " + str(test_date))

# getting month name using %B
res = test_date.strftime("%B")

# printing result
print("Month Name from Date : " + str(res))
```

**输出:**

```py
The original date is : 2020-04-08 00:00:00
Month Name from Date : April
```

### **方法二:使用** [**历库**](https://www.geeksforgeeks.org/python-calendar-module/) **和月号**

在这个变体中，不是将 datetime 对象作为输入，而是接受月份名称作为输入，结果是返回的月份名称。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get Month Name from Month Number
# Using calendar library and month number
import calendar

# initializing month number
test_num = 5

# printing original month number
print("The original month number is : " + str(test_num))

# using month_name() to get month name 
res = calendar.month_name[test_num]

# printing result
print("Month Name from Number : " + str(res))
```

**输出:**

```py
The original month number is : 5
Month Name from Number : May
```