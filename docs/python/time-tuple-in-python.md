# Python 中的时间元组

> 原文:[https://www.geeksforgeeks.org/time-tuple-in-python/](https://www.geeksforgeeks.org/time-tuple-in-python/)

**先决条件:** [Python 日期时间模块示例](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

在 Python 中，[日期时间](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)模块用于操作日期和时间对象。这个模块有不同的函数和类来处理日期和时间解析、格式化和算术运算。日期时间模块有各种常量如`MINYEAR`、`MAXYEAR`等，各种类如`datetime.date`、`datetime.time`、`datetime.datetime`等，各种实例方法如日期对象的`replace()`、`weekday()`、`isocalendar()`等，以及`time()`、`dst()`、`timestamp()`等。时间对象的。

#### 时间表()

为了使用`timetuple()`方法，我们需要导入日期时间模块。 **timetuple()** 方法是日期时间模块的实例方法，该方法返回`time.struct_time`对象。`time.struct_time`对象的属性可以通过属性的索引或名称来访问。`struct_time`对象具有用于表示日期和时间字段的属性，这些属性存储在元组中:

T16】TM _ monT18】1 至 12T21T26】TM _ mdayT28】1 至 31 【T29 T61T64】一周中的某一天 T66】TM _ wdayT68】0 至 6T71T74】一天

| 索引 | 属性 | 田 | 域 |
| --- | --- | --- | --- |
| 0 | 4 位数年 | TM _ 年 | 例:2020 |
| 1 | 月 |
| 2 | 日 |
| 5 | 第二 | tm_sec | 0 至 61 |
| 6 | 7 |

**注意:**`tm_isdst`属性是一个标志，当夏令时活动关闭时设置为 0，如果夏令时活动则设置为 1，如果夏令时由编译器确定，则设置为-1，`tm_yday`属性基于儒略日数，在`tm_sec`中，值 60 或 61 是闰秒。

**示例 1:** 以下示例显示了当前日期的时间元组。

```py
# program to illustrate timetuple()
# method in Python

import datetime

# creating object
obj = datetime.datetime.today()

# obtaining the attributes of the
# datetime instance as a tuple
objTimeTuple = obj.timetuple()

# displaying the tuples of the object
print(objTimeTuple)
```

**输出:**

> time . struct _ time(TM _ year = 2020，tm_mon=1，tm_mday=29，tm_hour=14，tm_min=13，tm_sec=32，tm_wday=2，tm_yday=29，tm_isdst=-1)

在上述程序中，`datetime`对象`obj`被赋予当前日期，然后使用`timetuple()`方法获取元组中`obj`的属性并显示。我们也可以用一个循环来显示`obj`的属性。

**示例 2:** 让我们看另一个使用自定义日期的示例。

```py
# program to illustrate timetuple() 
# method in Python 

import datetime

# creating object and initializing
# it with custom date
birthDate = datetime.datetime(1999, 4, 6)

# obtaining the attributes and displaying them
print("Year: ", birthDate.timetuple()[0])
print("Month: ", birthDate.timetuple()[1])
print("Day: ", birthDate.timetuple()[2])
print("Hour: ", birthDate.timetuple()[3])
print("Minute: ", birthDate.timetuple()[4])
print("Second: ", birthDate.timetuple()[5])
print("Day of Week: ", birthDate.timetuple()[6])
print("Day of Year: ", birthDate.timetuple()[7])
print("Daylight Saving Time: ", birthDate.timetuple()[8])
```

**输出:**

```py
Year:  1999
Month:  4
Day:  6
Hour:  0
Minute:  0
Second:  0
Day of Week:  1
Day of Year:  96
Daylight Saving Time:  -1
```

这里`datetime`对象`birthDate`被分配了一个自定义日期，然后该对象的每个属性由元组的索引显示。从`time.struct_time`结构中检索的参数可以作为元组的元素访问，年、月和日字段被指定为 datetime 对象(这里是 1999、4 和 6)，涉及小时、分钟、秒的字段被设置为零。