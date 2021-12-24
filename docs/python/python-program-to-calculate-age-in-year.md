# Python 程序以年为单位计算年龄

> 原文:[https://www . geesforgeks . org/python-计算程序-年龄/](https://www.geeksforgeeks.org/python-program-to-calculate-age-in-year/)

给定 y/m/d 格式的出生日期，编写 Python 程序，以年为单位查找当前年龄。

**示例:**

```py
Input : 1997/2/3
Output : 21 years (for present year i.e 2018)

Input : 2010/12/25
Output : 8 years (for present year i.e 2018)
```

**方法# 1:**
以年为单位寻找当前年龄的天真方法是找到当前年份和出生年份之间的差异。参考这里的[的天真方法。](https://www.geeksforgeeks.org/program-calculate-age/)

**方法 2:** 使用 datetime 模块
Python 提供了 datetime 模块来处理 Python 中所有与 datetime 相关的问题。使用日期时间，我们可以通过从当前年份中减去出生年份来找到年龄。与此同时，我们需要关注出生月份和生日。为此，我们检查当前月份和日期是否小于出生月份和日期。如果是，年龄减 1，否则减 0。

## 蟒蛇 3

```py
# Python3 code to  calculate age in years

from datetime import date

def calculateAge(birthDate):
    today = date.today()
    age = today.year - birthDate.year -
         ((today.month, today.day) <
         (birthDate.month, birthDate.day))

    return age

# Driver code
print(calculateAge(date(1997, 2, 3)), "years")
```

**Output:** 

```py
21 years
```

**方法#3 :** 高效日期时间方法
上述方法不处理特殊情况，即出生日期为 2 月 29 日且当年不是闰年。这种情况必须作为例外提出，因为出生日期的计算可能不准确。此方法包括尝试并捕获此异常。

## 蟒蛇 3

```py
# Python3 code to  calculate age in years
from datetime import date

def calculateAge(born):
    today = date.today()
    try:
        birthday = born.replace(year = today.year)

    # raised when birth date is February 29
    # and the current year is not a leap year
    except ValueError:
        birthday = born.replace(year = today.year,
                  month = born.month + 1, day = 1)

    if birthday > today:
        return today.year - born.year - 1
    else:
        return today.year - born.year

# Driver code
print(calculateAge(date(1997, 2, 3)), "years")
```

**Output:** 

```py
21 years
```

**方法#4:** 使用除法
在该方法中，我们计算从出生日期到当前日期的日期数。将日期数除以一年中的天数，即 365.2425。

## 蟒蛇 3

```py
# Python3 code to  calculate age in years
from datetime import date

def calculateAge(birthDate):
    days_in_year = 365.2425   
    age = int((date.today() - birthDate).days / days_in_year)
    return age

# Driver code
print(calculateAge(date(1997, 2, 3)), "years")
```

**Output:** 

```py
21 years
```