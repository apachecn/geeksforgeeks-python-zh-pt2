# Python 程序打印当前年、月、日

> 原文:[https://www . geesforgeks . org/python-程序转打印-当前年-月-日/](https://www.geeksforgeeks.org/python-program-to-print-current-year-month-and-day/)

在本文中，任务是编写一个 Python 程序来打印当前的年、月和日。

**方法:**

*   In Python, in order to print the current date composed of year, month and day, it has a module named [datetime](https://www.geeksforgeeks.org/python-datetime-module-with-examples/) . From the DateTime module, import the date class
*   Create an object of the date class
*   Call today () function of date class to get today's date.
*   By using the created object, we can print today's year, month and day (attributes of date class).

## 蟒 3

```py
# importing date class from datetime module
from datetime import date

# creating the date object of today's date
todays_date = date.today()

# printing todays date
print("Current date: ", todays_date)

# fetching the current year, month and day of today
print("Current year:", todays_date.year)
print("Current month:", todays_date.month)
print("Current day:", todays_date.day)
```

**输出:**

```py
Current date:  2020-12-10
Current year: 2020
Current month: 12
Current day: 10
```