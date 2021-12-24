# Python 统计模块中的 mode()函数

> 原文:[https://www . geesforgeks . org/python-statistics-mode-function/](https://www.geeksforgeeks.org/python-statistics-mode-function/)

一组数据值的**模式**是**最常出现的值**。它是数据最有可能被采样的值。连续概率分布的模式通常被认为是其**概率密度函数具有局部最大值的任何值 x，因此任何峰值都是模式。**
Python 在统计和处理一组大范围的值时非常健壮。统计模块有大量的函数来处理非常大的数据集。mode()函数就是这样的方法之一。该函数返回给定数据集范围内中心数据点的稳健度量。

**示例:**

```py
Given data-set is :  [1, 2, 3, 4, 4, 4, 4, 5, 6, 7, 7, 7, 8]
The mode of the given data-set is 4
Logic: 4 is the most occurring/ most common element from the given list 
```

```py
Syntax :
mode([data-set])
Parameters : 
[data-set] which is a tuple, list or a iterator of 
real valued numbers as well as Strings.
Return type : 
Returns the most-common data point from discrete or nominal data.
Errors and Exceptions : 
Raises StatisticsError when data set is empty.
```

**代码#1 :** 本文将通过一个简单的例子演示 mode()函数。

## 蟒蛇 3

```py
# Python code to demonstrate the
# use of mode() function

# mode() function a sub-set of the statistics module
# We need to import the statistics module before doing any work
import statistics

# declaring a simple data-set consisting of real valued
# positive integers.
set1 =[1, 2, 3, 3, 4, 4, 4, 5, 5, 6]

# In the given data-set
# Count of 1 is 1
# Count of 2 is 1
# Count of 3 is 2
# Count of 4 is 3
# Count of 5 is 2
# Count of 6 is 1
# We can infer that 4 has the highest population distribution
# So mode of set1 is 4

# Printing out mode of given data-set
print("Mode of given data set is % s" % (statistics.mode(set1)))
```

**Output**

```py
Mode of given data set is 4
```

**代码#2 :** 在这段代码中，我们将演示各种数据集的 mode()函数。

## 蟒蛇 3

```py
# Python code to demonstrate the
# working of mode() function
# on a various range of data types

# Importing the statistics module
from statistics import mode

# Importing fractions module as fr
# Enables to calculate harmonic_mean of a
# set in Fraction
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (2, 3, 3, 4, 5, 5, 5, 5, 6, 6, 6, 7)

# tuple of a set of floating point values
data2 = (2.4, 1.3, 1.3, 1.3, 2.4, 4.6)

# tuple of a set of fractional numbers
data3 = (fr(1, 2), fr(1, 2), fr(10, 3), fr(2, 3))

# tuple of a set of negative integers
data4 = (-1, -2, -2, -2, -7, -7, -9)

# tuple of strings
data5 = ("red", "blue", "black", "blue", "black", "black", "brown")

# Printing out the mode of the above data-sets
print("Mode of data set 1 is % s" % (mode(data1)))
print("Mode of data set 2 is % s" % (mode(data2)))
print("Mode of data set 3 is % s" % (mode(data3)))
print("Mode of data set 4 is % s" % (mode(data4)))
print("Mode of data set 5 is % s" % (mode(data5)))
```

**Output**

```py
Mode of data set 1 is 5
Mode of data set 2 is 1.3
Mode of data set 3 is 1/2
Mode of data set 4 is -2
Mode of data set 5 is black
```

**代码#3 :** 在这段代码中将演示何时出现**统计错误**

## 蟒蛇 3

```py
# Python code to demonstrate the 
# statistics error in mode function

'''
StatisticsError is raised while using mode when there are
two equal modes present in a data set and when the data set
is empty or null
'''

# importing statistics module
import statistics

# creating a data set consisting of two equal data-sets
data1 =[1, 1, 1, -1, -1, -1]

# In the above data set
# Count of 1 is 3
# Count of -1 is also 3
# StatisticsError will be raised

print(statistics.mode(data1))
```

**输出**

```py
Traceback (most recent call last):
  File "/home/38fbe95fe09d5f65aaa038e37aac20fa.py", line 20, in 
    print(statistics.mode(data1))
  File "/usr/lib/python3.5/statistics.py", line 474, in mode
    raise StatisticsError('no mode for empty data') from None
statistics.StatisticsError: no mode for empty data
```

> 注意:在 Python 的较新版本中，如 Python 3.8，当一个序列有多个模式时，实际的数学概念将被应用，其中，最小的元素被认为是一个模式。
> 
> 比方说，对于上面的代码，频率-1 和 1 是相同的，但是-1 将是模式，因为它的值较小。

**应用:**mode()是一个统计函数，主要用于金融行业，将价值/价格与过去的详细信息进行比较，根据价格分布集计算/预测未来可能的价格。mean()不是单独使用的，而是与另外两个统计支柱 mean 和 median 一起创建了一个非常强大的工具，可以用来揭示数据的任何方面。