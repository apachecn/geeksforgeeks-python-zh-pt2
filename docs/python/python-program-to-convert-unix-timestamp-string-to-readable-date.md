# Python 程序将 unix 时间戳字符串转换为可读日期

> 原文:[https://www . geesforgeks . org/python-程序到转换-UNIX-时间戳-字符串到可读日期/](https://www.geeksforgeeks.org/python-program-to-convert-unix-timestamp-string-to-readable-date/)

在本文中，我们将看到 Unix 时间戳字符串到可读日期的转换。这可以借助 **fromtimestamp()** 和**str time()**功能来完成。

## 使用的功能

**from timestamp():****from timestamp()**功能用于返回指定时间戳对应的日期和时间。

**注意:**这里的时间戳是从 1970 年到 2038 年，如果时间戳中有闰秒，这个函数不考虑。这个函数是一个类方法。

> **语法:** @classmethod fromtimestamp(时间戳)
> 
> **参数:**该函数接受如下所示的参数:
> 
> *   **时间戳:**这是要返回日期的指定时间戳。
> 
> **返回值:**该函数返回指定时间戳对应的日期和时间。

**str time():****str time()**函数用于将日期和时间对象转换为其字符串表示形式。它接受一个或多个格式化代码输入，并返回字符串表示形式。

> **语法：** strftime（格式）
> 
> **参数:**该函数接受单个参数，如下图所示:
> 
> *   **格式:**这是指定的日期时间对象。
> 
> **返回值:**返回日期或时间对象的字符串表示形式。

#### 让我们看看将指定的 Unix 时间戳字符串转换为可读日期的示例

**示例 1:** 转换指定的 Unix 时间戳字符串。

## 计算机编程语言

```
# Python program to illustrate the
# conversion of unix timestamp string
# to its readable date

# Importing datetime module
import datetime

# Calling the fromtimestamp() function to
# extract datetime from the given timestamp

# Calling the strftime() function to convert
# the extracted datetime into its string format
print(datetime.datetime.fromtimestamp(int("1294113662"))
      .strftime('%Y-%m-%d %H:%M:%S'))
```

**输出:**

```
2011-01-04 04:01:02
```

**示例 2:** 转换指定的 Unix 时间戳字符串。

## 计算机编程语言

```
# Python program to illustrate the
# conversion of unix timestamp string
# to its readable date

# Importing datetime module
import datetime

# Calling the fromtimestamp() function to
# extract datetime from the given timestamp
timestamp = datetime.datetime.fromtimestamp(1200001234)

# Calling the strftime() function to convert
# the extracted datetime into its string format
print(timestamp.strftime('%Y-%m-%d %H:%M:%S'))
```

**输出:**

```
2008-01-10 21:40:34
```