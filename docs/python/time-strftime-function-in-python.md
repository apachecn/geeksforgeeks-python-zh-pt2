# Python 中的 time.strftime()函数

> 原文:[https://www . geesforgeks . org/time-strftime-function-in-python/](https://www.geeksforgeeks.org/time-strftime-function-in-python/)

由于**时间模块**提供了各种与时间相关的功能。因此有必要导入时间模块，否则会因为时间模块中存在 **time.strftime(格式[，t])** 的定义而出错。
**time.strftime(format[，t])** 函数将表示由 gmtime()或 localtime()返回的时间的 tuprl 或 struct_time 转换为由 format 参数指定的字符串。
如果没有提供 t，则使用 localtime()返回的当前时间。格式必须是字符串。如果 t 中的任何字段超出了允许的范围，则*值错误*会出现。
**注:**
0 是时间元组中任意位置的合法参数；如果它通常是非法的，则该值被强制为正确的值。

> **语法:**time . str time(格式[，t])
> **参数:**
> **t**–要格式化的时间秒数
> **格式**–这是字符串类型。即指令可以嵌入格式字符串中。
> **返回值:**无

格式字符串中可以嵌入的指令有很多，可以在这里引用。
T3【备注:T5】

*   当与 strptime()函数一起使用时，如果%I 指令用于分析小时，则%p 指令只影响输出小时字段。
*   范围真的是 0 到 61；值 60 在代表闰秒的时间戳中有效，并且出于历史原因，值 61 是受支持的。
*   与 strptime()函数一起使用时，%U 和%W 仅在指定了星期几和年份的计算中使用。

下面是实现:

## 蟒蛇 3

```py
# Program To show How can we use different derivatives
# Multiple at a time and single at a time

# importing the srtftime() and gmtime()
# if not used the gm time, time changes
# to the local time

from time import gmtime, strftime

# using simple format of showing time
s = strftime("%a, %d %b %Y %H:%M:%S + 1010", gmtime())
print("Example 1:", s)

print()

# only change in this is the full names
# and the representation
s = strftime("%A, %D %B %Y %H:%M:%S + 0000", gmtime())
print("Example 2:", s)

print()

# this will show you the preferred date time format
s = strftime("%c")
print("Example 3:", s)

print()

# this will tell about the centuries
s = strftime("%C")
print("Example 4:", s)

print()

# MOTY: month of the year
# DOTY: Day of the year
# Simple representation
# % n - new line
s = strftime("%A, %D %B %Y, %r, %nMOTY:%m %nDOTY:% j")
print("Example 5:", s)

print()

# % R - time in 24 hour notation
s = strftime(" %R ")
print("Example 6:", s)

print()

# % H - hour, using a 24-hour clock (00 to 23) in Example 1, 2, 3
# % I - hour, using a 12-hour clock (01 to 12)
s = strftime("%a, %d %b %Y %I:%M:%S + 0000", gmtime())
print("Example 7:", s)

print()

# % T - current time, equal to % H:% M:% S
s = strftime("%r, %T ", gmtime())
print("Example 8:", s)

print()

# % u an % U use (see difference)
s = strftime("%r, %u, %U")
print("Example 9:", s)

print()

# use of % V, % W, % w
s = strftime("%r, %V, %W, %w")
print("Example 10:", s)

print()

# use of % x, % X, % y, % Y
s = strftime("%x, %X, %y, %Y")
print("Example 11:", s)

print()

# use of % Z, % z
s = strftime("%r, %z, %Z")
print("Example 12:", s)
```

**Output:** 

```py
Example 1: Tue, 25 Jun 2019 10:09:52 + 1010

Example 2: Tuesday, 06/25/19 June 2019 10:09:52 + 0000

Example 3: Tue Jun 25 10:09:52 2019

Example 4: 20

Example 5: Tuesday, 06/25/19 June 2019, 10:09:52 AM, 
MOTY:06 
DOTY:% j

Example 6:  10:09 

Example 7: Tue, 25 Jun 2019 10:09:52 + 0000

Example 8: 10:09:52 AM, 10:09:52 

Example 9: 10:09:52 AM, 2, 25

Example 10: 10:09:52 AM, 26, 25, 2

Example 11: 06/25/19, 10:09:52, 19, 2019

Example 12: 10:09:52 AM, +0000, UTC
```