# 替换 Python 中 Datetime.date 类的()函数

> 原文:[https://www . geesforgeks . org/replace-of-function-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/replace-function-of-datetime-date-class-in-python/)

**replace()** 函数用于操作 DateTime 模块的 DateTime 类的对象。通常，它会替换日期(年、月、日)，并返回一个新的日期时间对象。

> **语法:**替换(年=自.年，月=自.月，日=自.日)
> 
> **参数:**
> 
> *   **年:**新年值(区间:1 < =年< = 9999)
> *   **月:**新月值(范围:1 < =月< = 12)
> *   **日:**新日值(范围:1 < =日< = 31)
> 
> **返回:**新的日期时间对象。

**示例 1:** 用 datetime 对象替换年份。

## 蟒蛇 3

```
# import module
from datetime import date

# Creating an instance
# of datetime
Date = date(2010, 2, 12)
print("Original date : ", Date)

# Using replace() method
New_date = Date.replace(year=2021)
print("After Modify the year:", New_date)
```

**Output**

```
Original date :  2010-02-12
After Modify the year: 2021-02-12

```

**示例 2:** 用 datetime 对象替换月份。

## 蟒蛇 3

```
# import module
from datetime import date

# Creating an instance
# of datetime
Date = date(2010, 2, 12)
print("Original date : ", Date)

# Using replace() method
New_date = Date.replace(month=5)
print("After Modify the month:", New_date)
```

**Output**

```
Original date :  2010-02-12
After Modify the month: 2010-05-12

```

**示例 3:** 将日期替换为 datetime 对象。

## 蟒蛇 3

```
# import module
from datetime import date

# Creating an instance
# of datetime
Date = date(2010, 2, 12)
print("Original date : ", Date)

# Using replace() method
New_date = Date.replace(day=21)
print("After Modify the day:", New_date)
```

**Output**

```
Original date :  2010-02-12
After Modify the day: 2010-02-21

```

**例 4:** 用 datetime 对象替换时间。

## 蟒蛇 3

```
from datetime import datetime

Date = datetime(2010, 2, 12, 8, 50, 23)
print("Original date and time : ", Date)

New_date = Date.replace(hour=1,
                        minute=3,
                        second=12)
print("After modify date and time : ", New_date)
```

**Output**

```
Original date and time :  2010-02-12 08:50:23
After modify date and time :  2010-02-12 01:03:12

```