# Python 统计模块中的中位数()函数

> 原文:[https://www.geeksforgeeks.org/python-statistics-median/](https://www.geeksforgeeks.org/python-statistics-median/)

说到数据分析和统计，Python 是一种非常流行的语言。幸运的是，Python3 提供了统计模块，该模块附带了非常有用的函数，如 mean()、median()、mode()等。统计模块中的
**中值()**函数可用于计算未排序数据列表的中值。使用中值()函数的最大优点是，数据列表在作为参数发送到中值()函数之前不需要排序。
中值是将数据样本或概率分布的上半部分与下半部分分开的值。对于数据集，它可以被认为是中间值。中位数是统计学和概率论中数据集性质的中心趋势的度量。中值相对于平均值有一个非常大的优势，即中值不会被非常大或非常小的值扭曲太多。中值要么包含在所提供的数据集中，要么不会对所提供的数据产生太大影响。
对于*奇数*元素集，中间值为中间值。
对于*甚至*的元素集合，中值是两个中间元素的平均值。

```
Median can be represented by the following formula :

```

> **语法:** **中值(** ***【数据集】*** **)**
> **参数:**
> **【数据集】**:列表或元组或带有一组数值的可迭代表
> **返回:**返回包含数据的可迭代表的中值(中间值)
> **异常:** **统计错误【T28】**

**代码#1 :** 工作

## 蟒蛇 3

```
# Python code to demonstrate the 
# working of median() function.

# importing statistics module
import statistics

# unsorted list of random integers
data1 = [2, -2, 3, 6, 9, 4, 5, -1]

# Printing median of the
# random data-set
print("Median of data-set is : % s "
        % (statistics.median(data1)))
```

**输出:**

```
Median of data-set is : 3.5 
```

**代码#2 :**

## 蟒蛇 3

```
# Python code to demonstrate the
# working of median() on various
# range of data-sets

# importing the statistics module
from statistics import median

# Importing fractions module as fr
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (2, 3, 4, 5, 7, 9, 11)

# tuple of floating point values
data2 = (2.4, 5.1, 6.7, 8.9)

# tuple of fractional numbers
data3 = (fr(1, 2), fr(44, 12),
         fr(10, 3), fr(2, 3))

# tuple of a set of  negative integers
data4 = (-5, -1, -12, -19, -3)

# tuple of set of positive
# and negative integers
data5 = (-1, -2, -3, -4, 4, 3, 2, 1)

# Printing the median of above datasets
print("Median of data-set 1 is % s" % (median(data1)))
print("Median of data-set 2 is % s" % (median(data2)))
print("Median of data-set 3 is % s" % (median(data3)))
print("Median of data-set 4 is % s" % (median(data4)))
print("Median of data-set 5 is % s" % (median(data5)))
```

**输出:**

```
Median of data-set 1 is 5
Median of data-set 2 is 5.9
Median of data-set 3 is 2
Median of data-set 4 is -5
Median of data-set 5 is 0.0
```

**代码#3 :** 演示统计错误

## 蟒蛇 3

```
# Python code to demonstrate
# StatisticsError of median()

# importing the statistics module
from statistics import median

# creating an empty data-set
empty = []

# will raise StatisticsError
print(median(empty))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/3c98774036f97845ee9f65f6d3571e49.py", line 12, in 
    print(median(empty))
  File "/usr/lib/python3.5/statistics.py", line 353, in median
    raise StatisticsError("no median for empty data")
statistics.StatisticsError: no median for empty data
```

**应用:**
在实际应用中，不同的离散度和种群趋势的度量是根据相应种群值的估计程度进行比较的。例如，比较表明，当数据未被来自重尾数据分布或来自混合数据分布的数据污染时，样本均值在统计上比样本中值更有效，但在其他方面效率较低，并且样本中值的效率高于大范围分布的效率。更具体地说，与最小方差均值(对于大的正态样本)相比，中值有 64%的效率。