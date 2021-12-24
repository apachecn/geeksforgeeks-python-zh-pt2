# Python–钟摆模块

> 原文:[https://www.geeksforgeeks.org/python-pendulum-module/](https://www.geeksforgeeks.org/python-pendulum-module/)

钟摆是流行的 Python 日期时间库之一，用于简化日期时间操作。它提供了一个更干净、更容易使用的应用编程接口。它简化了涉及时区的复杂日期操作问题，而时区在本机日期时间实例中无法正确处理。

它继承了标准的 datetime 库，但提供了更好的功能。因此，您可以在已经在使用内置 datetime 类的项目中引入钟摆 Datetime 实例(通过使用类似 sqlite3 的类型函数检查对象类型的库除外)。

**要安装该模块，请在您的终端中运行以下命令:**

```
pip install pendulum
```

**我们来看看简单的例子:**

您可以使用各种方法创建日期时间实例，如 datetime()、local()、now()、from_format()。

**示例:**

## 蟒蛇 3

```
# import library
import pendulum
dt = pendulum.datetime(2020, 11, 27)
print(dt)

#local() creates datetime instance with local timezone
local = pendulum.local(2020, 11,27)
print(local)
print(local.timezone.name)
```

**输出:**

```
2020-11-27T00:00:00+00:00
2020-11-27T00:00:00+05:30
Asia/Calcutta
```

## 转换时区

您可以使用 in_timezone()方法或直接使用时区库来转换时区。为了更好地理解，请参考以下示例

**注:** UTC(协调世界时)是世界调节时钟和时间的主要时间标准。

**示例:**

## 蟒蛇 3

```
# Importing library
import pendulum

# Getting current UTC time
utc_time = pendulum.now('UTC')

# Switching current timezone to
# Kolkata timezone using in_timezone().
kolkata_time = utc_time.in_timezone('Asia/Kolkata')
print('Current Date Time in Kolkata =', kolkata_time)

# Generating Sydney timezone
sydney_tz = pendulum.timezone('Australia/Sydney')

# Switching current timezone to
# Sydney timezone using convert().
sydney_time = sydney_tz.convert(utc_time)
print('Current Date Time in Sydney =', sydney_time)
```

**输出:**

```
Current Date Time in Kolkata = 2020-11-27T15:16:36.985136+05:30
Current Date Time in Sydney = 2020-11-27T20:46:36.985136+11:00
```

## 日期时间操作

对于日期时间操作，我们可以使用 add()和减法()方法。每个方法都返回一个新的日期时间实例。

**示例:**

## 蟒蛇 3

```
# Importing the library
import pendulum
# creating datetime instance
dt = pendulum.datetime(2020, 11, 27)
print(dt)

# Manipulating datetime object using add()
dt = dt.add(years=5)
print(dt)

# Manipulating datetime object using subtract()
dt = dt.subtract(months = 1)
print(dt)

# Similarly you can add or subtract
# months,weeks,days,hours,minutes
# individually or all at a time.
dt = dt.add(years=3, months=2, days=6,
            hours=12, minutes=30, seconds=45)

print(dt)
```

**输出:**

```
2020-11-27T00:00:00+00:00
2025-11-27T00:00:00+00:00
2025-10-27T00:00:00+00:00
2029-01-02T12:30:45+00:00
```

## 日期时间格式

我们可以使用以下方法将日期时间转换为标准格式的字符串。

*   截止日期字符串()
*   to _ formatted _ date _ string()
*   to_time_string()
*   to_datetime_string()
*   to_day_datetime_string()

摆锤模块还有 format()& str time()函数，我们可以在这里指定自己的格式。

**示例:**

## 蟒蛇 3

```
import pendulum
# Creating new DateTime instance
dt = pendulum.datetime(2020, 11, 27, 12, 30, 15)
print(dt)

# Formatting date-time
dt.to_day_datetime_string()
formatted_str = dt.format('dddd Do [of] MMMM YYYY HH:mm:ss A')
print(formatted_str)

new_str = dt.strftime('%Y-%m-%d %H:%M:%S %Z%z')
print(new_str)
```

**输出:**

```
2020-11-27T12:30:15+00:00
Friday 27th of November 2020 12:30:15 PM
2020-11-27 12:30:15 UTC+0000
```

## 将字符串解析为日期时间

parse()函数用于将具有常用格式的字符串解析为 datetime 对象。如果要传递非标准或更复杂的字符串，请使用 from_format()函数。但是，如果您希望库依赖于 dateutil 解析器，您必须传递 strict=False。

## 蟒蛇 3

```
import pendulum
dt = pendulum.parse('1997-11-21T22:00:00',
                    tz = 'Asia/Calcutta')
print(dt)

# parsing of non standard string
dt = pendulum.from_format('2020/11/21',
                          'YYYY/MM/DD')

print(dt)
```

**输出:**

```
1997-11-21T22:00:00+05:30
2020-11-21T00:00:00+00:00
```

## 持续时间–时间增量更换

持续时间类继承自本机时间增量类。但是，它的行为略有不同。

**示例:**

## 蟒蛇 3

```
import pendulum
time_delta = pendulum.duration(days = 2,
                               hours = 10,
                               years = 2)
print(time_delta)

# Date when i am writing this code is 2020-11-27.
print('future date =',
      pendulum.now() + time_delta)
```