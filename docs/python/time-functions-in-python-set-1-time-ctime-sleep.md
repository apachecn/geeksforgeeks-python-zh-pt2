# Python 中的时间函数| Set 1 (time()、ctime()、sleep()……)

> 原文:[https://www . geesforgeks . org/time-functions-in-python-set-1-time-ctime-sleep/](https://www.geeksforgeeks.org/time-functions-in-python-set-1-time-ctime-sleep/)

Python 定义了一个[模块](https://www.geeksforgeeks.org/python-modules/)，“时间”，它允许我们处理关于时间的各种操作，它的转换和表示，在生活中的各种应用中找到了它的用途。时间的开始是从 1970 年 1 月 1 日上午 12:00 开始测量的，这个时间在 Python 中被称为“**纪元**”。

**准时运行:**

**1。时间()** :-该功能用于统计自纪元以来经过的**秒的数量。

**2。gmtime(秒)** :-该函数返回一个**结构，该结构有 9 个值**，每个值依次表示一个时间属性。它将**秒转换为时间属性(日、年、月等)。)**直到从纪元开始的指定秒。如果没有提到秒，时间计算到现在。结构属性表如下。**

```
Index   Attributes   Values
 0        tm_year     2008
 1        tm_mon      1 to 12
 2        tm_mday     1 to 31
 3        tm_hour     0 to 23
 4        tm_min      0 to 59
 5        tm_sec      0 to 61 (60 or 61 are leap-seconds)
 6        tm_wday     0 to 6 
 7        tm_yday     1 to 366
 8        tm_isdst    -1, 0, 1 where -1 means 
                               Library determines DST
```

## 计算机编程语言

```
# Python code to demonstrate the working of
# time() and gmtime()

#  importing "time" module for time operations
import time

# using time() to display time since epoch
print ("Seconds elapsed since the epoch are : ",end="")
print (time.time())

# using gmtime() to return the time attribute structure
print ("Time calculated acc. to given seconds is : ")
print (time.gmtime())
```

**输出:**

```
Seconds elapsed since the epoch are : 1470121951.9536893
Time calculated acc. to given seconds is : 
time.struct_time(tm_year=2016, tm_mon=8, tm_mday=2,
tm_hour=7, tm_min=12, tm_sec=31, tm_wday=1, 
tm_yday=215, tm_isdst=0)
```

**3。asctime("time")** :-该函数采用由 gmtime()产生的时间属性字符串，并返回表示时间的 **24 字符串**。

**4。ctime(秒)** :-该函数返回一个 **24 个字符的时间字符串**，但以秒为参数，**计算到所述秒的时间**。如果没有传递参数，时间会计算到现在。

## 计算机编程语言

```
# Python code to demonstrate the working of
# asctime() and ctime()

#  importing "time" module for time operations
import time

# initializing time using gmtime()
ti = time.gmtime()

# using asctime() to display time acc. to time mentioned
print ("Time calculated using asctime() is : ",end="")
print (time.asctime(ti))

# using ctime() to display time string using seconds
print ("Time calculated using ctime() is : ", end="")
print (time.ctime())
```

**输出:**

```
Time calculated using asctime() is : Tue Aug  2 07:47:02 2016
Time calculated using ctime() is : Tue Aug  2 07:47:02 2016
```

**5。睡眠(秒)** :-该方法用于**在参数中指定的时间内暂停程序执行**。

## 计算机编程语言

```
# Python code to demonstrate the working of
# sleep()

#  importing "time" module for time operations
import time

# using ctime() to show present time
print ("Start Execution : ",end="")
print (time.ctime())

# using sleep() to hault execution
time.sleep(4)

# using ctime() to show present time
print ("Stop Execution : ",end="")
print (time.ctime())
```

**输出:**

```
Start Execution : Tue Aug  2 07:59:03 2016
Stop Execution : Tue Aug  2 07:59:07 2016
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。