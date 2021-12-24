# Python 中的统计函数|集合 1(中心位置的平均值和度量)

> 原文:[https://www . geesforgeks . org/statistical-functions-python-set-1 averages-measure-central-location/](https://www.geeksforgeeks.org/statistical-functions-python-set-1averages-measure-central-location/)

Python 能够使用文件“ **statistics** ”操作一些统计数据，并计算各种统计操作的结果，在数学领域非常有用。

**中心位置函数的重要平均值和度量值**:

**1。mean()** :-该函数返回在其参数中传递的数据的**平均值或平均值**。如果传递的参数为空，则会引发**统计错误**。

**2。模式()** :-该功能返回出现次数最多的**号**。如果传递的参数为空，则会出现**统计错误**。

```py
# Python code to demonstrate the working of
# mean() and mode()

# importing statistics to handle statistical operations
import statistics

# initializing list
li = [1, 2, 3, 3, 2, 2, 2, 1]

# using mean() to calculate average of list elements
print ("The average of list values is : ",end="")
print (statistics.mean(li))

# using mode() to print maximum occurring of list elements
print ("The maximum occurring element is  : ",end="")
print (statistics.mode(li))
```

输出:

```py
The average of list values is : 2.0
The maximum occurring element is  : 2

```

**3。中位数()** :-此函数用于计算中位数，即数据的**中间元素。**如果传递的参数为空，则会出现**统计错误**。

**4。median_low()** :-该函数返回奇数个元素的数据中值，但如果是偶数个元素，则返回中间两个元素的**下值。如果传递的参数为空，则会引发**统计错误**。**

**5。median_high()** :-该函数返回奇数元素情况下的数据中值，但偶数元素情况下，**返回中间两个**元素中较高的一个。如果传递的参数为空，则会出现**统计错误**。

```py
# Python code to demonstrate the working of
# median(), median_low() and median_high()

# importing statistics to handle statistical operations
import statistics

# initializing list
li = [1, 2, 2, 3, 3, 3]

# using median() to print median of list elements
print ("The median of list element is : ",end="")
print (statistics.median(li))

# using median_low() to print low median of list elements
print ("The lower median of list element is : ",end="")
print (statistics.median_low(li))

# using median_high() to print high median of list elements
print ("The higher median of list element is : ",end="")
print (statistics.median_high(li))
```

输出:

```py
The median of list element is : 2.5
The lower median of list element is : 2
The higher median of list element is : 3

```

**6。中位数 _ group()**:-该函数用于计算组中位数，即数据的**第 50 百分位**。如果传递的参数为空，则会出现**统计错误**。

```py
# Python code to demonstrate the working of
# median_grouped()

# importing statistics to handle statistical operations
import statistics

# initializing list
li = [1, 2, 2, 3, 3, 3]

# using median_grouped() to calculate 50th percentile
print ("The 50th percentile of data is : ",end="")
print (statistics.median_grouped(li))
```

输出:

```py
The 50th percentile of data is : 2.5

```

[Python 中的统计函数|集合 2(扩展的度量)](https://www.geeksforgeeks.org/statistical-functions-in-python-set-2-measure-of-spread/)

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。