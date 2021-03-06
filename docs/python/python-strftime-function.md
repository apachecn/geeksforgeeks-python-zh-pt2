# Python strftime（） 函数

> [https://www.geeksforgeeks.org/python-strftime-function/](https://www.geeksforgeeks.org/python-strftime-function/)

**str time()**函数用于将日期和时间对象转换为它们的字符串表示。它接受一个或多个格式化代码输入，并返回字符串表示形式。

**语法:**

```py
strftime(format)

```

**返回:**返回日期或时间对象的字符串表示形式。

**格式代码列表:**格式代码参考表。

| 指示的 | 意义 | 输出格式 |
| --- | --- | --- |
| %a | 缩写的工作日名称。 | 珊，我的… |
| %A | 完整的工作日名称。 | 星期天，星期一，… |
| %w | 以十进制数表示的工作日。 | 0, 1, …, 6 |
| %d | 一个月中的某一天，以零加十进制表示。 | 01, 02, …, 31 |
| %-d | 以十进制数表示的一个月中的某一天。 | 1, 2, …, 30 |
| %b | 缩写的月份名称。 | 一月，二月，…，十二月 |
| %B | 完整的月份名称。 | 一月，二月，… |
| %m | 月是一个加零的十进制数。 | 01, 02, …, 12 |
| %-m | 以十进制数表示的月份。 | 1, 2, …, 12 |
| %y | 没有世纪的年份是加零的十进制数。 | 00, 01, …, 99 |
| %-y | 没有世纪作为十进制数的年份。 | 0, 1, …, 99 |
| %Y | 以世纪为十进制数的年份。 | 2013 年、2019 年等。 |
| %H | 小时(24 小时制)作为加零的十进制数。 | 00, 01, …, 23 |
| %-H | 小时(24 小时制)作为十进制数。 | 0, 1, …, 23 |
| %I | 小时(12 小时制)作为加零的十进制数。 | 01, 02, …, 12 |
| %-我 | 小时(12 小时制)作为十进制数。 | 1, 2, … 12 |
| %p | 区域设置的上午或下午。 | 上午，下午 |
| %M | 分钟是一个加零的十进制数。 | 00, 01, …, 59 |
| %-M | 分钟作为十进制数。 | 0, 1, …, 59 |
| %S | 第二个是加零的十进制数。 | 00, 01, …, 59 |
| %-S | 第二个十进制数。 | 0, 1, …, 59 |
| %f | 微秒为十进制数，左边加零。 | 000000 – 999999 |
| %z | 以+HHMM 或-HHMM 形式表示的世界协调时偏移量。 |   |
| %Z | 时区名称。 |   |
| %j | 以零加十进制数表示的一年中的某一天。 | 001, 002, …, 366 |
| %-j | 以十进制数表示的一年中的某一天。 | 1, 2, …, 366 |
| %U | 一年中的周数(周日是一周的第一天)。新年第一个星期日之前的所有日子都被认为是第 0 周。 | 00, 01, …, 53 |
| %W | 一年中的周数(星期一是一周的第一天)。新年第一个星期一之前的所有日子都被认为是在第 0 周。 | 00, 01, …, 53 |

**示例:**

```py
# Python program to demonstrate
# strftime() function

from datetime import datetime as dt

# Getting current date and time
now = dt.now()
print("Without formatting", now)

# Example 1
s = now.strftime("%a %m %y")
print('\nExample 1:', s)

# Example 2
s = now.strftime("%A %-m %Y")
print('\nExample 2:', s)

# Example 3
s = now.strftime("%-I %p %S")
print('\nExample 3:', s)

# Example 4
s = now.strftime("%-j")
print('\nExample 4:', s)
```

**输出:**

```py
Without formatting 2019-12-17 18:21:39.211378

Example 1: Tue-12-19

Example 2: Tuesday-12-2019

Example 3: 6 PM 39

Example 4: 351

```