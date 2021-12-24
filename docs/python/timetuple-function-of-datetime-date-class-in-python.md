# Python 中 Datetime.date 类的 timetuple()函数

> 原文:[https://www . geesforgeks . org/time tuple-of-function-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/timetuple-function-of-datetime-date-class-in-python/)

timetuple()方法返回一个 time.struct time 对象，它是一个命名元组。命名元组对象具有可由索引或名称访问的属性。struct time 对象具有日期和时间字段的属性，以及指定夏令时是否有效的标志。timetuple()方法提供的命名元组的年、月和日字段将根据 date 对象进行设置，但小时、分钟和秒的值将设置为零。返回对象上的夏令时标志将设置为-1。time.struct time 对象的特征可以通过索引或属性名来访问。struct time 对象包含用于表示日期和时间字段的属性，这些属性保存在元组中:

<figure class="table">

| **指数** | **属性** | **值** |
| --- | --- | --- |
| Zero | tm _ 年(年) | 任何一年 |
| one | 周一(月) | 1 至 12 |
| Two | 今日(日) | 1 至 31 岁 |
| three | tm 小时(小时) | 0 到 23 |
| four | 分钟 | 0 至 59 |
| five | 秒(秒) | 0 至 61 |
| six | 一周中的某一天 | 0 到 6 |
| seven | 一年中的某一天 | 1 至 366 |
| eight | 夏令时 | -1, 0, 1 |

</figure>

**示例 1:** 将()与当前日期相匹配。

这里我们将演示当前日期的时间对()。当前日期被分配给 DateTime 对象，timetuple()函数用于检索元组中对象的属性，然后显示元组。循环也可以用来显示对象的特征。

## 蟒蛇 3

```py
import datetime

# creating current date object
currentDate = datetime.datetime.today()

# datetime instance's attributes
# are returned as a tuple.
currentDateTimeTuple = currentDate.timetuple()

# showing the object's tuples
print(currentDateTimeTuple)
print()
print("Using a for loop, output the tuple values :")

for value in currentDateTimeTuple:
    print(value)
```

**输出:**

> time.struct_time(tm_year=2021，tm_mon=8，tm_mday=2，tm_hour=18，tm_min=32，tm_sec=56，tm_wday=0，tm_yday=214，tm_isdst=-1)
> 
> 使用 for 循环，输出元组值:
> 
> Two thousand and twenty-one
> 
> eight
> 
> Two
> 
> Eighteen
> 
> Thirty-two
> 
> Fifty-six
> 
> Zero
> 
> Two hundred and fourteen
> 
> -1

**示例 2:** 带有特定日期的 timetuple()。

考虑另一个场景，我们利用圣诞节日期。创建日期时间对象圣诞节，然后元组的索引显示该对象的每个属性。

## 蟒蛇 3

```py
import datetime

# creating xmas date object
xmas = datetime.datetime(2021, 12, 25)

# datetime instance's attributes
# are returned as a tuple.
xmasTimeTuple = xmas.timetuple()

# showing the object's tuples
print(xmasTimeTuple)
```

**输出:**

```py
time.struct_time(tm_year=2021, tm_mon=12, tm_mday=25, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=5, tm_yday=359, tm_isdst=-1)
```