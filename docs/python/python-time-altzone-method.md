# Python 时间 altzone()方法

> 原文:[https://www.geeksforgeeks.org/python-time-altzone-method/](https://www.geeksforgeeks.org/python-time-altzone-method/)

**Python altzone()方法**用于返回本地 DST 时区的偏移量，以 UTC 以西的秒为单位。我们还可以通过使用时区和 altzone 方法获得当前时区和世界协调时之间的当前时间。

**语法:**

```
time.altzone
```

**示例:**

## 蟒蛇 3

```
# import the time module
import time

# display altzone
print(time.altzone)
```

**输出:**

```
25200
```

**示例:** Python 程序使用时区和 altzone 方法获取当前时区和 UTC 之间的当前时间

## 蟒蛇 3

```
# import time module
import time

# get_zone function to get the
# current time between current time zone and UTC
# by using timezone  and altzone method
def get_zone():
    dst = time.daylight and time.localtime().tm_isdst

    # get altzone if there exists dst otherwise
    # get timezone
    offset = time.altzone if dst else time.timezone

    # check if offset greater than 0
    westerly = offset > 0

    # get the minutes and seconds
    minutes, seconds = divmod(abs(offset), 60)
    hours, minutes = divmod(minutes, 60)

    # return the timezone
    return '{}{:02d}{:02d}'.format('-' if westerly else '+', hours, minutes)

# call the function
get_zone()
```

**输出:**

```
+0000
```