# Python 中 Datetime.date 类的 weekday()函数

> 原文:[https://www . geesforgeks . org/weekday-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/weekday-function-of-datetime-date-class-in-python/)

datetime.date 类函数的 **weekday()** 用于返回一周中指定一天对应的整数值。

> **语法:**工作日()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回一周中指定一天对应的整数映射。下表显示了对应于一周中某一天的整数值。

<figure class="table">

| weekday()函数返回的整数 | 一周中的某一天 |
| --- | --- |
| Zero | 星期一 |
| one | 星期二 |
| Two | 星期三 |
| three | 星期四 |
| four | 星期五 |
| five | 星期六 |
| six | 星期日 |

</figure>

**例 1:** 获取一周中指定天数对应的整数值。

## 蟒蛇 3

```
# Python3 code for getting
# integer value corresponding
# to the specified day of the week

# Importing datetime module
import datetime

# Specifying some date and time values
dateTimeInstance1 = datetime.datetime(2021, 8, 1, 00, 00, 00)
dateTimeInstance2 = datetime.datetime(2021, 8, 2, 00, 00, 00)
dateTimeInstance3 = datetime.datetime(2021, 8, 3, 00, 00, 00)

# Calling the weekday() functions over the
# above dateTimeInstances
dayOfTheWeek1 = dateTimeInstance1.weekday()
dayOfTheWeek2 = dateTimeInstance2.weekday()
dayOfTheWeek3 = dateTimeInstance3.weekday()

# Getting the integer value corresponding
# to the specified day of the week
print(dayOfTheWeek1)
print(dayOfTheWeek2)
print(dayOfTheWeek3)
```

**输出:**

```
6
0
1
```

**示例 2:** 获取日期和时间以及一周中的一天的名称。

## 蟒蛇 3

```
# Python3 code for getting
# integer value corresponding
# to the specified day of the week.

# Importing datetime module
import datetime

# Mapping of the week day
weekDaysMapping = ("Monday", "Tuesday",
                   "Wednesday", "Thursday",
                   "Friday", "Saturday",
                   "Sunday")

# Specifying a date and time value
dateTimeInstance = datetime.datetime(2021, 8, 2,
                                     00, 00, 00)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[dateTimeInstance.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(dateTimeInstance, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=3)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=4)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=5)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=6)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=7)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))

# Getting on next day
nextDay = dateTimeInstance.replace(day=8)

# Calling the weekday() function over the above
# specified weekday and date time value
dayOfTheWeek = weekDaysMapping[nextDay.weekday()]

# Printing the date and time along with the
# corresponding week day name
print("{} is for {}".format(nextDay, dayOfTheWeek))
```

**输出:**

```
2021-08-02 00:00:00 is for Monday
2021-08-03 00:00:00 is for Tuesday
2021-08-04 00:00:00 is for Wednesday
2021-08-05 00:00:00 is for Thursday
2021-08-06 00:00:00 is for Friday
2021-08-07 00:00:00 is for Saturday
2021-08-08 00:00:00 is for Sunday
```