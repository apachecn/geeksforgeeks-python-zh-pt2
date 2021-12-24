# Python–time . ctime()方法

> 原文:[https://www.geeksforgeeks.org/python-time-ctime-method/](https://www.geeksforgeeks.org/python-time-ctime-method/)

Python **time.ctime()** 方法将纪元后的时间(秒)转换为本地时间的字符串。这相当于 as time(local time(秒))。当前时间由 localtime 返回()当时间元组不存在时使用。

> **语法:** time.ctime([秒])
> 
> **参数:**
> 
> *   **秒:**转换为字符串表示的秒数。

**例 1:**

让我们带着解释进入代码:

## 蟒蛇 3

```py
# import module
import time

# here no parameter is passed
print(time.ctime())
```

**输出:**

```py
Thu Mar 18 11:00:19 2021
```

它打印相当于 asctime()方法的标准时间。

**例 2:**

我们来看看**as time()**方法:

## 蟒蛇 3

```py
# import time
import time

# gives local time
a = time.localtime() 
c = time.asctime(a)
print(c)
```