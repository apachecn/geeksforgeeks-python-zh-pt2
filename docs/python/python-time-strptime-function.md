# Python 时间 strptime()函数

> 原文:[https://www . geesforgeks . org/python-time-strptime-function/](https://www.geeksforgeeks.org/python-time-strptime-function/)

Python 中的 strptime()函数用于格式化和返回日期和时间的字符串表示形式。它接受日期、时间或两者作为输入，并根据给它的指令对其进行解析。如果无法根据提供的指令格式化字符串，它将引发 ValueError。

**语法:**

```
time.strptime(date_time_srting,directive)
```

在这里，

*   date_time_string:这是一个必要的字符串参数，其中提供了要格式化的日期。
*   指令:此参数表示解析给定字符串的条件。这也是一个必要的参数。

### 可定向:

下表列出了 python 中支持的指令。

<figure class="table">

| **格式代码** | **意为** | **例** |
| --- | --- | --- |
| %a | 缩写的工作日名称 | 珊，我的天 |
| %A | 完整的工作日名称 | 星期天，星期一 |
| %w | 以十进制数表示的工作日 | 0…6 |
| %d | 以零填充十进制表示的一个月中的某一天 | 01, 02 |
| %b | 缩写的月份名称 | 一月，二月 |
| %m | 月是零填充的十进制数 | 01, 02 |
| %B | 完整月份名称 | 一月，二月 |
| %y | 没有世纪的年份作为零填充的十进制数 | 99, 00  |
| %Y | 以世纪为十进制数的年份 | 2000, 1999 |
| %H | 小时(24 小时制)作为零填充十进制数 | 01, 23 |
| %I | 小时(12 小时制)作为零填充十进制数 | 01, 12 |
| %p | 区域设置的上午或下午 | 上午，下午 |
| %M | 分钟作为零填充的十进制数 | 01, 59 |
| %S | 第二个是零填充的十进制数 | 01, 59 |
| %f | 微秒为十进制数，左边填充零 | 000000, 999999 |
| %z | 世界协调时偏移量，格式为+HHMM 或-HHMM |   |
| %Z | 时区名称 |   |
| %j | 以零填充的十进制数表示的一年中的某一天 | 001, 365 |
| %U | 一年中的第几周(星期日是第一周) | 0, 6 |
| %W | 一年中的周数 | 00, 53 |
| %c | 区域设置的适当日期和时间表示 | 2013 年 9 月 30 日 07:06:05 |
| %x | 区域设置的适当日期表示 | 11/30/98 |
| %X | 区域的适当时间表示 | 10:03:43 |
| %% | 文字“%”字符 | % |

</figure>

### **示例 1: Python 字符串至今**

## 蟒蛇 3

```
import time

formatted_date = time.strptime(" 02 Dec 1996",
                               " %d %b %Y")
print(formatted_date)
```

**输出:**

> time.struct_time(tm_year=1996，tm_mon=12，tm_mday=2，tm_hour=0，tm_min=0，tm_sec=0，tm_wday=0，tm_yday=337，tm_isdst=-1)

### **示例 2: Python 字符串到日期和时间**

## 蟒蛇 3

```
import time

print(time.strptime("02/12/1996 5:53","%m/%d/%Y %H:%M"))
```

**输出:**

> time.struct_time(tm_year=1996，tm_mon=2，tm_mday=12，tm_hour=5，tm_min=53，tm_sec=0，tm_wday=0，tm_yday=43，tm_isdst=-1)

### **例 3:数值误差**

在本例中，如果时间指令不匹配，则发生错误。

## 蟒蛇 3

```
import time as datetime

datetime_str = '08/1/18 3:55:6'

try:
    datetime_object = datetime.strptime(datetime_str, '%m/%d/%y')
except ValueError as e:
    print('ValueError Raised:', e)

time_str = '25::55::26'

try:
    time_object = time.strptime(time_str, '%H::%M::%S')
except ValueError as e:
    print('ValueError:', e)
```

**输出:**

```
ValueError Raised: unconverted data remains:  3:55:6
ValueError: time data '25::55::26' does not match format '%H::%M::%S'
```