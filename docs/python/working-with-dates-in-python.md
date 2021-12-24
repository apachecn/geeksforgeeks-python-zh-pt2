# 在 Python 中处理日期

> 原文:[https://www.geeksforgeeks.org/working-with-dates-in-python/](https://www.geeksforgeeks.org/working-with-dates-in-python/)

在本文中，我们将讨论如何使用 python 处理日期。

Python 使得处理日期和时间变得非常容易，我们所要做的就是导入 python 附带的名为 [DateTime](https://www.geeksforgeeks.org/python-datetime-module/) 的模块。这是一种更有效的处理日期的方式，不需要显式编程。通过使用此模块，您将从本地计算机所在的时区获得时间和日期。这个模块只是从主机获取日期和时间(在这种情况下，它是您执行程序的计算机)。

## 日期类别

在深入研究功能之前。让我们从一个简单的程序开始，该程序使用 datetime 模块中的 date 对象返回今天的日期。

**语法:**

> date.today()

**示例:**获取当前日期

## 蟒蛇 3

```
# importing the module
from datetime import date

# storing today's date in a variable
today = date.today()

# Printing the variable
print(f"Today's date: {today}")
```

**输出:**

> 今日日期:2021-09-28

***今天()*** 方法会给你当前日期所在的时区。如果你只需要年或月或日，那么你可以使用这个方法与各自的关键词。

**示例:**获取日期属性方式

## 蟒蛇 3

```
from datetime import date

today = date.today()

# to print the present year
print(f"Present Year:{today.year}")

# to print the present month
print(f"Present Month:{today.month}")

# to print the present date
print(f"Present Date:{today.day}")
```

**输出:**

```
Present Year:2021
Present Month:9
Present Date:28
```

**示例:**计算从当前日期到特定日期的天数的程序

## 蟒蛇 3

```
# Importing date from Datetime module
from datetime import date

# Storing today's date into a variable
today = date.today()

# Storing the specific date
graduation_day = date(2023, 8, 11)

# finding the difference of today's date from 
# specified date
days_left = abs(graduation_day - today)

# Displaying the no.of.days left without time
print(f"Number of days left till graduation: {days_left}")
```

**输出:**

```
Number of days left till graduation: 682 days, 0:00:00
```

## 日期时间类

该方法类似于 date 方法，但这是 date 对象的升级版本，它将从本地系统获取日期和时间。让我们编写相同的程序，我们为日期对象编写的程序，但这次是用时间计算剩余的天数。

**示例:**计算剩余天数的程序

## 蟒蛇 3

```
from datetime import datetime

# By using now(), We will get both current 
# date and time Storing current time and
# date into a variable
today = datetime.now()

# Storing the date and time you want to calculate
# In this you have to give the time as the input
graduation_day = datetime(2023, 8, 11, 0, 0, 0)

# finding the difference from
days_left = abs(graduation_day - today)

# Displaying the no.of.days left with time
print(f"Time left till the graduation: {days_left}")
```

**输出:**

> 离毕业还有 681 天，22:12:03.851113

## 时间增量类

这个对象允许我们在特定的日期和时间上加上或减去时间或日期。

**语法:**

> datetime.timedelta(天=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)

**例:**加减时间

## 蟒蛇 3

```
from datetime import datetime, timedelta

# adding 9 hours
hour_delta = timedelta(hours=9)

# Storing the new date
timeAdded = datetime.now() + hour_delta

# Displaying current date and time with 
# adding 9 hours
print(f"The date after adding 9 hours: {timeAdded}")

# adding 1 day
day_delta = timedelta(days=1)

# storing the new date
dateAdded = datetime.now() + day_delta

# Displaying current date and time with 
# adding 1 day
print(f"The date after adding 1 day: {dateAdded}")
```

**输出:**

> 加 9 小时后的日期:2021-09-28 10:49:39.577570
> 
> 添加 1 天后的日期:2021-09-29 01:49:39.577570

## 解析和格式化

如果我们想将日期转换成可读的字符串，则使用***【str time()***方法。

**语法:**

```
time.strftime(format, t)
```

**参数:**

*   **格式–**这是字符串类型。即指令可以嵌入格式字符串中。
*   **t–**要格式化的时间。

**示例:**将日期转换为字符串

## 蟒蛇 3

```
import datetime

today = datetime.datetime(2021, 9, 10, 12, 30, 30)

print(today.strftime("%H:%M:%S %B %d %Y"))
```

**输出:**

```
12:30:30 September 10 2021
```

**解析**用于将字符串转换为日期时间格式。***str time()***就是用来执行这个的。参数分别是 date_string 和 format。

**语法:**

> stroptime(date _ string 格式)

**示例:**将日期时间转换为字符串

## 蟒蛇 3

```
from datetime import datetime

print(datetime.strptime('26/5/2020', '%d/%m/%Y'))
```

**输出:**

```
2020-05-26 00:00:00
```