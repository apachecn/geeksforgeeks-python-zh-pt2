# 现在在 Python 中()函数

> 原文:[https://www.geeksforgeeks.org/python-now-function/](https://www.geeksforgeeks.org/python-now-function/)

Python 库定义了一个主要用于获取当前时间和日期的函数。 ***现在()*** 功能返回当前本地日期和时间，在`datetime` 模块下定义。

> 语法: **datetime.now(tz)**
> 
> **参数:**
> **tz :** 需要当前时间和日期的指定时区。(默认使用格林威治子午线时间。)
> 
> **返回:**以时间格式返回当前日期和时间。

**代码#1 :**

```py
# Python3 code to demonstrate
# Getting current time using 
# now().

# importing datetime module for now()
import datetime

# using now() to get current time
current_time = datetime.datetime.now()

# Printing value of now.
print ("Time now at greenwich meridian is : "
                                    , end = "")
print (current_time)
```

输出:

```py
Time now at greenwich meridian is : 2018-03-29 10:26:23.473031

```

#### now()的属性:

now()有不同的属性，与年、月、日、时、分、秒等时间属性相同。

**代码#2 :** 演示 now()的属性。

```py
# Python3 code to demonstrate
# attributes of now()

# importing datetime module for now()
import datetime

# using now() to get current time
current_time = datetime.datetime.now()

# Printing attributes of now().
print ("The attributes of now() are : ")

print ("Year : ", end = "")
print (current_time.year)

print ("Month : ", end = "")
print (current_time.month)

print ("Day : ", end = "")
print (current_time.day)

print ("Hour : ", end = "")
print (current_time.hour)

print ("Minute : ", end = "")
print (current_time.minute)

print ("Second : ", end = "")
print (current_time.second)

print ("Microsecond : ", end = "")
print (current_time.microsecond)
```

```py
The attributes of now() are : 
Year : 2018
Month : 3
Day : 26
Hour : 20
Minute : 9
Second : 4
Microsecond : 499806

```

#### 获取特定时区的时间:

有时，需要的只是获取特定时区的当前时间。now()将时区作为输入，给出面向时区的输出时间。但是这些时区是在 **pytz** 库中定义的。

**代码#3 :** 使用 now()处理特定时区。

```py
# Python3 code to demonstrate
# attributes of now() for timezone

# for now()
import datetime

# for timezone()
import pytz

# using now() to get current time
current_time = datetime.datetime.now(pytz.timezone('Asia / Calcutta'))

# printing current time in india
print ("The current time in india is : ")
print (current_time) 
```

输出:

```py
The current time in india is : 
2018-03-29 03:09:33.878000+05:30

```

**注意:**由于缺少 *pytz* 模块，上述代码在联机 IDE 上无法工作。

**应用:**
在开发任何真实世界的应用时，我们可能需要显示任何时区的实时时间。现在()函数可以非常高效轻松地完成这里的工作。