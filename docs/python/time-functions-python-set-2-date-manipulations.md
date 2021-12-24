# Python 中的时间函数| Set-2(日期操作)

> 原文:[https://www . geesforgeks . org/time-functions-python-set-2-date-manuals/](https://www.geeksforgeeks.org/time-functions-python-set-2-date-manipulations/)

一些时间函数在[集合 1](https://www.geeksforgeeks.org/time-functions-in-python-set-1-time-ctime-sleep/) 中讨论

也可以使用 Python 使用“日期时间”模块并在其中使用“日期”类来执行日期操作。

**日期操作:**

**1。MINYEAR** :-显示可以用日期类表示的**最小年份**。

**2。MAXYEAR** :-显示可以用日期类表示的**最大年份**。

```py
# Python code to demonstrate the working of
# MINYEAR and MAXYEAR

# importing built in module datetime
import datetime
from datetime import date

# using MINYEAR to print minimum representable year
print ("Minimum representable year is : ",end="")
print (datetime.MINYEAR)

# using MAXYEAR to print maximum representable year
print ("Maximum representable year is : ",end="")
print (datetime.MAXYEAR)
```

输出:

```py
Minimum representable year is : 1
Maximum representable year is : 9999

```

**3。date(yyyy-mm-dd)** :-该函数返回一个字符串，该字符串带有按年、月和日期顺序传递的参数。

**4。today()** :-以 yyyy-mm-dd 格式返回当前的**日期。**

```py
# Python code to demonstrate the working of
# date() and today()

# importing built in module datetime
import datetime
from datetime import date

# using date() to represent date
print ("The represented date is : ",end="")
print (datetime.date(1997,4,1))

# using today() to print present date
print ("Present date is : ",end="")
print (date.today())
```

输出:

```py
The represented date is : 1997-04-01
Present date is : 2016-08-02

```

**5。fromtimestamp(秒)** :-它返回从参数中提到的纪元开始经过的秒数计算出的**日期。**

**6。min()** :-返回可以用日期类表示的**最小日期**。

**7。max()** :-返回**最大日期**，可以用日期类表示。

```py
# Python code to demonstrate the working of
# fromtimestamp(), min() and max()

# importing built in module datetime
import datetime
from datetime import date

# using fromtimestamp() to calculate date
print ("The calculated date from seconds is : ",end="")
print (date.fromtimestamp(3452435))

# using min() to print minimum representable date
print ("Minimum representable date is : ",end="")
print (date.min)

# using max() to print minimum representable date
print ("Maximum representable date is : ",end="")
print (date.max)
```

输出:

```py
The calculated date from seconds is : 1970-02-09
Minimum representable date is : 0001-01-01
Maximum representable date is : 9999-12-31

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。