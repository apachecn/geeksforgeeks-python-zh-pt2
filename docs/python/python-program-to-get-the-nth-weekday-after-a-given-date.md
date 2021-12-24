# Python 程序获取给定日期后的第 n 个工作日

> 原文:[https://www . geesforgeks . org/python-程序-给定日期后的第 n 个工作日/](https://www.geeksforgeeks.org/python-program-to-get-the-nth-weekday-after-a-given-date/)

给定一个日期和工作日索引，任务是编写一个 Python 程序来获取给定日期之后一周中给定一天的日期。工作日指数基于下表:

<figure class="table">

| 索引 | 工作日 |
| --- | --- |
| Zero | 星期一 |
| one | 星期二 |
| Two | 星期三 |
| three | 星期四 |
| four | 星期五 |
| five | 星期六 |
| six | 星期日 |

</figure>

**示例:**

> **输入 ：** test_date = datetime.datetime（2017， 3， 14）， weekday_idx = 4
> 
> **产量:** 2017-03-17
> 
> **说明:**3 月 14 日为星期二，即 1 个工作日，第 4 个工作日为星期五，即 3 月 17 日。
> 
> **输入 ：** test_date = datetime.datetime（2017， 3， 12）， weekday_idx = 5
> 
> **产量:** 2017-03-18
> 
> **说明:**3 月 12 日为周日，即第 6 个工作日，下周第 5 个工作日为 Sturday，即 3 月 18 日。

**方法#1:使用** [**时间增量()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/) **+工作日()**

在这种情况下，我们从工作日索引中减去日期工作日，然后检查提取的所需索引，然后是所需的日期，如果是负数，则用 7 求和，然后使用 timedelta()将结果数字添加到当前日期。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Next weekday from Date
# Using timedelta() + weekday()
import datetime

# initializing dates
test_date = datetime.datetime(2017, 3, 14)

# printing original date
print("The original date is : " + str(test_date)[:10])

# initializing weekday index
weekday_idx = 4

# computing delta days
days_delta = weekday_idx - test_date.weekday()
if days_delta <= 0:
    days_delta += 7

# adding days to required result
res = test_date + datetime.timedelta(days_delta)

# printing result
print("Next date of required weekday : " + str(res)[:10])
```

**输出:**

```
The original date is : 2017-03-14
Next date of required weekday : 2017-03-17
```

**方法 2:使用**[**λ功能**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

使用 lambda 函数为这个问题提供了一个简洁的解决方案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Next weekday from Date
# Using lamnda function
import datetime

# initializing dates
test_date = datetime.datetime(2017, 3, 14)

# printing original date
print("The original date is : " + str(test_date)[:10])

# initializing weekday index
weekday_idx = 4

# lambda function provides one liner shorthand
def lfnc(test_date, weekday_idx): return test_date + \
    datetime.timedelta(days=(weekday_idx - test_date.weekday() + 7) % 7)

res = lfnc(test_date, weekday_idx)

# printing result
print("Next date of required weekday : " + str(res)[:10])
```

**输出:**

```
The original date is : 2017-03-14
Next date of required weekday : 2017-03-17
```