# Python 中的统计函数|集合 2(扩展的度量)

> 原文:[https://www . geesforgeks . org/statistical-functions-in-python-set-2-measure-of-spread/](https://www.geeksforgeeks.org/statistical-functions-in-python-set-2-measure-of-spread/)

[Python 中的统计函数|集合 1(中心位置的平均值和度量)](https://www.geeksforgeeks.org/statistical-functions-python-set-1averages-measure-central-location/)

本文讨论了统计分布函数的度量。

**1。方差()** :-该函数计算方差，即数据偏差的**度量，方差值越大，数据值分布越广**。假设数据是总体的一部分，样本方差在此函数中计算。如果传递的参数为空，则会引发**统计错误**。

**2。pvariance()** :-该函数计算整个人口的**方差。数据被解释为整个人口的数据。如果传递的参数为空，则会出现**统计错误**。**

```py
# Python code to demonstrate the working of 
# variance() and pvariance()

# importing statistics to handle statistical operations
import statistics

# initializing list
li = [1.5, 2.5, 2.5, 3.5, 3.5, 3.5]

# using variance to calculate variance of data
print ("The variance of data is : ",end="")
print (statistics.variance(li))

# using pvariance to calculate population variance of data
print ("The population variance of data is : ",end="")
print (statistics.pvariance(li))
```

输出:

```py
The variance of data is : 0.6666666666666667
The population variance of data is : 0.5555555555555556

```

**3。stdev()** :-该函数返回数据的**标准偏差(样本方差的平方根)**。如果传递的参数为空，则会引发**统计错误**。

**4。pstdev()** :-该函数返回数据的总体**标准偏差(总体方差的平方根)**。如果传递的参数为空，则会出现**统计错误**。

```py
# Python code to demonstrate the working of 
# stdev() and pstdev()

# importing statistics to handle statistical operations
import statistics

# initializing list
li = [1.5, 2.5, 2.5, 3.5, 3.5, 3.5]

# using stdev to calculate standard deviation of data
print ("The standard deviation of data is : ",end="")
print (statistics.stdev(li))

# using pstdev to calculate population standard deviation of data
print ("The population standard deviation of data is : ",end="")
print (statistics.pstdev(li))
```

输出:

```py
The standard deviation of data is : 0.816496580927726
The population standard deviation of data is : 0.7453559924999299

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。