# Python 统计|均值()函数

> 原文:[https://www . geesforgeks . org/python-statistics-mean-function/](https://www.geeksforgeeks.org/python-statistics-mean-function/)

先决条件:[统计函数介绍](https://www.geeksforgeeks.org/statistical-functions-python-set-1averages-measure-central-location/)
说到数据分析和统计，Python 是一种非常流行的语言。幸运的是，Python3 提供了统计模块，该模块附带了非常有用的函数，如 mean()、median()、mode()等。
**均值()**函数可用于计算给定数字列表的均值/平均值。它返回作为参数传递的数据集的平均值。
算术平均值是数据的总和除以数据点的数量。它是对一组范围不同的值中数据的中心位置的度量。在 Python 中，我们通常通过给定数字的总和除以当前数字的计数来实现这一点。

```
Given set of numbers : [n1, n2, n3, n5, n6]

Sum of data-set = (n1 + n2 + n3 + n4 + n5)
Number of data produced = 5

Average or arithmetic mean  = *(n1 + n2 + n3 + n4 + n5) / 5*
```

> **语法** : **表示(【数据集】)**
> **参数:**
> **【数据集】**:一组数字的列表或元组。
> **返回:**所提供数据集的样本算术平均值。
> **异常** :
> **当除数值以外的任何东西作为参数传递时，键入错误**。

**代码#1 :** 工作

## 蟒蛇 3

```
# Python program to demonstrate mean()
# function from the statistics module

# Importing the statistics module
import statistics

# list of positive integer numbers
data1 = [1, 3, 4, 5, 7, 9, 2]

x = statistics.mean(data1)

# Printing the mean
print("Mean is :", x)
```

输出:

```
 Mean is : 4.428571428571429
```

**代码#2 :** 工作

## 蟒蛇 3

```
# Python program to demonstrate mean()
# function from the statistics module

# Importing the statistics module
from statistics import mean

# Importing fractions module as fr
# Enables to calculate mean of a
# set in Fraction
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (11, 3, 4, 5, 7, 9, 2)

# tuple of a negative set of integers
data2 = (-1, -2, -4, -7, -12, -19)

# tuple of mixed range of numbers
data3 = (-1, -13, -6, 4, 5, 19, 9)

# tuple of a set of fractional numbers
data4 = (fr(1, 2), fr(44, 12), fr(10, 3), fr(2, 3))

# dictionary of a set of values
# Only the keys are taken in
# consideration by mean()
data5 = {1:"one", 2:"two", 3:"three"}

# Printing the mean of above datasets
print("Mean of data set 1 is % s" % (mean(data1)))
print("Mean of data set 2 is % s" % (mean(data2)))
print("Mean of data set 3 is % s" % (mean(data3)))
print("Mean of data set 4 is % s" % (mean(data4)))
print("Mean of data set 5 is % s" % (mean(data5)))
```

**输出:**

```
Mean of data set 1 is 5.857142857142857
Mean of data set 2 is -7.5
Mean of data set 3 is 2.4285714285714284
Mean of data set 4 is 49/24
Mean of data set 5 is 2
```

**代码#3 :** 类型错误

## 蟒蛇 3

```
# Python3 code to demonstrate TypeError

# importing statistics module
from statistics import mean

# While using dictionaries, only keys are
# taken into consideration by mean()
dic = {"one":1, "three":3, "seven":7,
       "twenty":20, "nine":9, "six":6}

# Will raise TypeError
print(mean(dic))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/9f8a941703745a24ddce5b5f6f211e6f.py", line 29, in 
    print(mean(dic))
  File "/usr/lib/python3.5/statistics.py", line 331, in mean
    T, total, count = _sum(data)
  File "/usr/lib/python3.5/statistics.py", line 161, in _sum
    for n, d in map(_exact_ratio, values):
  File "/usr/lib/python3.5/statistics.py", line 247, in _exact_ratio
    raise TypeError(msg.format(type(x).__name__))
TypeError: can't convert type 'str' to numerator/denominator
```

**应用:**
均值/算术平均值是非常重要的函数之一，同时处理统计数据和大值。因此，使用 mean()这样的函数，可以从大数据集中提取趋势值和特征值。