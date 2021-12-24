# Python 程序获取当前时间

> 原文:[https://www . geesforgeks . org/python-program-to-get-current-time/](https://www.geeksforgeeks.org/python-program-to-get-current-time/)

在本文中，我们将了解在 Python 中获取当前时间的方法。有多种方法可以得到它。在 Python 中，最好使用日期时间模块来创建包含日期和时间的对象。
**1:时区的当前时间–**使用 pytZ 模块

```
from datetime import *
import pytz

tz_INDIA = pytz.timezone('Asia/Kolkata') 
datetime_INDIA = datetime.now(tz_INDIA)
print("INDIA time:", datetime_INDIA.strftime("%H:%M:%S"))
```

**输出:**

```
INDIA time: 19:29:53
```

**2:当前时间–**使用日期时间对象

**例 1:**

```
from datetime import datetime

# now() method is used to
# get object containing 
# current date & time.
now_method = datetime.now()

# strftime() method used to
# create a string representing
# the current time.
currentTime = now_method.strftime("%H:%M:%S")
print("Current Time =", currentTime)
```

**输出:**

```
Current Time = 19:31:51

```

**例 2:**

```
from datetime import datetime

# Time object containing 
# the current time.
time = datetime.now().time() 

print("Current Time =", time)
```

**输出:**

```
Current Time = 19:33:29.087840
```

**3。获取时间–**使用时间模块。

```
import time

# localtime() method used to
# get the object containing
# the local time.
Time = time.localtime()

# strftime() method used to
# create a string representing
# the current time.
currentTime = time.strftime("%H:%M:%S", Time)
print(currentTime)
```

**输出:**

```
19:35:17
```