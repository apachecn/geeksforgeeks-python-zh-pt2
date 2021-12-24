# Python–验证字符串日期格式

> 原文:[https://www . geesforgeks . org/python-validate-string-date-format/](https://www.geeksforgeeks.org/python-validate-string-date-format/)

给定一个日期格式和一个字符串日期，任务是编写一个 python 程序来检查日期是否有效以及是否与格式匹配。

**示例:**

> **输入:** test_str = '04-01-1997 '，格式= "%d-%m-%Y "
> 
> **输出:**真
> 
> **说明:**格式与日期匹配。
> 
> **输入:** test_str = '04-14-1997 '，格式= "%d-%m-%Y "
> 
> **输出:**假
> 
> **说明:**月不能为 14。

### **方法#1:使用 str time()**

在这种情况下，通常用于将字符串日期转换为 datetime 对象的函数 strptime 在与格式或日期不匹配时用作，会引发 ValueError，因此可用于计算有效性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Validate String date format
# Using strptime()
from datetime import datetime

# initializing string
test_str = '04-01-1997'

# printing original string
print("The original string is : " + str(test_str))

# initializing format
format = "%d-%m-%Y"

# checking if format matches the date
res = True

# using try-except to check for truth value
try:
    res = bool(datetime.strptime(test_str, format))
except ValueError:
    res = False

# printing result
print("Does date match format? : " + str(res))
```

**输出:**

```py
The original string is : 04-01-1997
Does date match format? : True
```

### **方法 2:使用 dateutil.parser.parse()**

在本文中，我们使用不同的内置函数 dateutil.parser 来检查已验证的格式。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Validate String date format
# Using dateutil.parser.parse
from dateutil import parser

# initializing string
test_str = '04-01-1997'

# printing original string
print("The original string is : " + str(test_str))

# initializing format
format = "%d-%m-%Y"

# checking if format matches the date
res = True

# using try-except to check for truth value
try:
    res = bool(parser.parse(test_str))
except ValueError:
    res = False

# printing result
print("Does date match format? : " + str(res))
```

**输出:**

```py
The original string is : 04-01-1997
Does date match format? : True
```