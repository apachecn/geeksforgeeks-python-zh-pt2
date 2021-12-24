# Python 统计模块中的 stdev()方法

> 原文:[https://www.geeksforgeeks.org/python-statistics-stdev/](https://www.geeksforgeeks.org/python-statistics-stdev/)

Python 中的[统计](https://www.geeksforgeeks.org/statistical-functions-in-python-set-2-measure-of-spread/)模块提供了一个名为 **stdev()** 的函数，可以用来计算标准差。stdev()函数只计算数据样本的标准差，而不是整个总体的标准差。

为了计算整个总体的标准差，使用了另一个称为 **pstdev()** 的函数。

***标准差*** 是统计学中对价差的度量。它用于量化一组数据值的传播和变化的度量。它非常类似于方差，给出偏差的度量，而方差提供平方值。
标准偏差的低测量值表示数据的分散程度较低，而标准偏差的高值表示一组数据与其平均值的分散程度不同。标准差的一个有用特性是，与方差不同，它是用与数据相同的单位表示的。

```py
Standard Deviation is calculated by :

where x1, x2, x3.....xn are observed values in sample data,
 is the mean value of observations and
N is the number of sample observations.
```

> **语法:** **stdev(【数据集】，xbar )**
> **参数:**
> **【数据】:**一个可与实数值相乘的项。
> **xbar** ***(可选)*** **:** 以数据集的实际平均值为值。
> **返回类型:**返回作为参数传递的值的实际标准偏差。
> **异常:**
> **统计对于少于 2 个作为参数传递的值的数据集，将引发错误**。当作为 *xbar* 提供的值与数据集的实际平均值不匹配时，
> **不可能/无精度值**。

**代码#1 :**

## 蟒蛇 3

```py
# Python code to demonstrate stdev() function

# importing Statistics module
import statistics

# creating a simple data - set
sample = [1, 2, 3, 4, 5]

# Prints standard deviation
# xbar is set to default value of 1
print("Standard Deviation of sample is % s "
                % (statistics.stdev(sample)))
```

**输出:**

```py
Standard Deviation of the sample is 1.5811388300841898 
```

**代码#2 :** 在一组不同的数据类型上演示 stdev()

## 蟒蛇 3

```py
# Python code to demonstrate stdev() 
# function on various range of datasets

# importing the statistics module
from statistics import stdev

# importing fractions as parameter values
from fractions import Fraction as fr

# creating a varying range of sample sets
# numbers are spread apart but not very much
sample1 = (1, 2, 5, 4, 8, 9, 12)

# tuple of a set of negative integers
sample2 = (-2, -4, -3, -1, -5, -6)

# tuple of a set of positive and negative numbers
# data-points are spread apart considerably
sample3 = (-9, -1, -0, 2, 1, 3, 4, 19)

# tuple of a set of floating point values
sample4 = (1.23, 1.45, 2.1, 2.2, 1.9)

# Print the standard deviation of 
# following sample sets of observations
print("The Standard Deviation of Sample1 is % s"
                              %(stdev(sample1)))

print("The Standard Deviation of Sample2 is % s"
                              %(stdev(sample2)))

print("The Standard Deviation of Sample3 is % s"
                              %(stdev(sample3)))

print("The Standard Deviation of Sample4 is % s"
                              %(stdev(sample4)))
```

**输出:**

```py
The Standard Deviation of Sample1 is 3.9761191895520196
The Standard Deviation of Sample2 is 1.8708286933869707
The Standard Deviation of Sample3 is 7.8182478855559445
The Standard Deviation of Sample4 is 0.41967844833872525
```

**代码#3 :** 演示方差()和 stdev()结果之间的差异

## 蟒蛇 3

```py
# Python code to demonstrate difference
# in results of stdev() and variance()

# importing Statistics module
import statistics

# creating a simple data-set
sample = [1, 2, 3, 4, 5]

# Printing standard deviation
# xbar is set to default value of 1
print("Standard Deviation of the sample is % s "
                    %(statistics.stdev(sample)))

# variance is approximately the
# squared result of what stdev is
print("Variance of the sample is % s"
     %(statistics.variance(sample)))
```

**输出:**

```py
Standard Deviation of the sample is 1.5811388300841898 
Variance of the sample is 2.5
```

**代码#4 :** 演示 **xbar** 参数的使用

## 蟒蛇 3

```py
# Python code to demonstrate use of xbar
# parameter while using stdev() function

# Importing statistics module
import statistics

# creating a sample list
sample = (1, 1.3, 1.2, 1.9, 2.5, 2.2)

# calculating the mean of sample set
m = statistics.mean(sample)

# xbar is nothing but stores
# the mean of the sample set

# calculating the variance of sample set
print("Standard Deviation of Sample set is % s"
         %(statistics.stdev(sample, xbar = m)))
```

**输出:**

```py
Standard Deviation of Sample set is 0.6047037842337906
```

**代码#5 :** 显示统计错误

## 蟒蛇 3

```py
# Python code to demonstrate StatisticsError

# importing the statistics module
import statistics

# creating a data-set with one element
sample = [1]

# will raise StatisticsError
print(statistics.stdev(sample))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/f921f9269b061f1cc4e5fc74abf6ce10.py", line 12, in 
    print(statistics.stdev(sample))
  File "/usr/lib/python3.5/statistics.py", line 617, in stdev
    var = variance(data, xbar)
  File "/usr/lib/python3.5/statistics.py", line 555, in variance
    raise StatisticsError('variance requires at least two data points')
statistics.StatisticsError: variance requires at least two data points
```

**应用:**

*   标准差在统计数学和统计研究领域非常重要。它通常用于测量统计计算中的置信度。例如，如果同一考试要进行多次，计算考试分数的误差幅度是通过计算结果的预期标准偏差来确定的。
*   它在金融研究领域非常有用，也有助于确定利润和亏损幅度。标准差也很重要，投资回报率的标准差是衡量投资波动性的指标。