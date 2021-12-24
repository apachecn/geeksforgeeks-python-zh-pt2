# Python time.timezone 常量

> 原文:[https://www . geesforgeks . org/python-time-time-time zone-constant/](https://www.geeksforgeeks.org/python-time-timezone-constant/)

**Python 时间。timezone** 常量以 UTC 格式返回本地(非 DST)时区偏移量，其中 DST 代表夏令时。西欧大部分地区为负，美国为正，英国为零)。此常数返回您当前所在的时区。

## 蟒蛇 3

```
import time

print(time.timezone)
```

**输出:**

```
-19800
```

### time.tzname

获取时区名称的类似函数是 time.tzname。它以元组的形式给出输出。元组包含两个字符串。第一个是该地区的非夏令时时区，第二个是该地区夏令时时区的名称。

## 蟒蛇 3

```
import time

print(time.tzname)
```

**输出:**

```
('India Standard Time', 'India Summer Time')
```

### 时间，旧区

它返回本地夏令时时区的偏移量，以世界协调时以西的秒为单位

## 蟒蛇 3

```
import time

print(time.altzone)
```

**输出:**

```
-23400
```

### 时间。白天

如果定义了夏令时时区，它将返回非零值

## 蟒蛇 3

```
import time

print(time.daylight)
```

**输出:**

```
0
```