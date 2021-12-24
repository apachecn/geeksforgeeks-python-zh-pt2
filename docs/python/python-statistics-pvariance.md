# Python 统计| pvariance()

> 原文:[https://www.geeksforgeeks.org/python-statistics-pvariance/](https://www.geeksforgeeks.org/python-statistics-pvariance/)

先决条件: [Python 统计|方差()](https://www.geeksforgeeks.org/python-statistics-variance/)
**pvariance()** 函数有助于计算整个样本的方差，而不是样本的方差。方差()和 pvariance()之间的唯一区别是，在使用方差()时，只考虑样本均值，而在 pvariance()期间，则考虑整个总体的均值。
总体方差只是类似于样本方差，它告诉我们特定人群中的数据点是如何分布的。它是从数据点到数据集平均值的距离的平均值，平方。总体方差是总体的一个参数，不依赖于研究方法或抽样实践。

> **语法:** **变量(【数据】，μ)**
> **参数:**
> **【数据】:**一个可与实值数进行迭代的变量。
> **亩(可选):**取数据集/种群的实际平均值为值。
> **返回类型:**返回作为参数传递的值的实际总体方差。
> **异常:**
> **统计对于作为参数传递的小于 2 值的数据集，将引发错误**。当作为*μ*提供的值与数据集的实际平均值不匹配时，
> **不可能值**。

**代码#1 :**

## 蟒蛇 3

```py
# Python code to demonstrate the
# use of pvariance()

# importing statistics module
import statistics

# creating a random population list
population = (1, 1.1, 1.2, 1.3, 1.4, 1.5, 1.9, 2.2,
              2.3, 2.4, 2.6, 2.9, 3.0, 3.4, 3.3, 3.2)

# Prints the population variance
print("Population variance is %s"
      %(statistics.pvariance(population)))
```

**输出:**

```py
Population variance is 0.6658984375
```

**代码#2 :** 演示不同范围的种群树上的 pvariance()。

## 蟒蛇 3

```py
# Python code to demonstrate pvariance()
# on various range of population sets

# importing statistics module
from statistics import pvariance

# importing fractions module as F
from fractions import Fraction as F

# Population tree for a set of positive integers
pop1 = (1, 2, 3, 5, 4, 6, 1, 2, 2, 3, 1, 3,
         7, 8, 9, 1, 1, 1, 2, 6, 7, 8, 9, )

# Creating a population tree for
# a set of negative integers
pop2 = (-36, -35, -34, -32, -30, -31, -33, -33, -33,
             -38, -36, -35, -34, -38, -40, -31, -32)

# Creating a population tree for
# a set of fractional numbers
pop3 = (F(1, 3), F(2, 4), F(2, 3),
        F(3, 2), F(2, 5), F(2, 2),
        F(1, 1), F(1, 4), F(1, 2), F(2, 1))

# Creating a population tree for
# a set of decimal values
pop4 = (3.45, 3.2, 2.5, 4.6, 5.66, 6.43,
        4.32, 4.23, 6.65, 7.87, 9.87, 1.23,
            1.00, 1.45, 10.12, 12.22, 19.88)

# Print the population variance for
# the created population trees
print("Population variance of set 1 is % s"
                        %(pvariance(pop1)))

print("Population variance of set 2 is % s"
                        %(pvariance(pop2)))

print("Population variance of set 3 is % s"
                        %(pvariance(pop3)))

print("Population variance of set 4 is % s"
                        %(pvariance(pop4)))
```

**输出:**

```py
Population variance of set 1 is 7.913043478260869
Population variance of set 2 is 7.204152249134948
Population variance of set 3 is 103889/360000
Population variance of set 4 is 21.767923875432526
```

**代码#3 :** 演示 **mu** 参数的使用。

## 蟒蛇 3

```py
# Python code to demonstrate the use
#  of 'mu' parameter on pvariance()

# importing statistics module
import statistics

# Apparently, the Python interpreter doesn't
# even check whether the value entered for mu
# is the actual mean of data-set or not.
# Thus providing incorrect value would
# lead to impossible answers

# Creating a population tree of the
# age of kids in a locality
tree = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11,
        12, 12, 12, 12, 13, 1, 2, 12, 2, 2,
              2, 3, 4, 5, 5, 5, 5, 6, 6, 6)

# Finding the mean of population tree
m = statistics.mean(tree)

# Using the mu parameter
# while using pvariance()
print("Population Variance is % s"
      %(statistics.pvariance(tree, mu = m)))
```

**输出:**

```py
Population Variance is 14.30385015608741
```

**代码#4 :** 演示方差()和方差()
之间的区别

## 蟒蛇 3

```py
# Python code to demonstrate the
# difference between pvariance()
# and variance()

# importing statistocs module
import statistics

# Population tree and extract
# a sample from it
tree = (1.1, 1.22, .23, .55, .67, 2.33, 2.81,
             1.54, 1.2, 0.2, 0.1, 1.22, 1.61)

# Sample extract from population tree
sample = (1.22, .23, .55, .67, 2.33,
               2.81, 1.54, 1.2, 0.2)

# Print sample variance and as
# well as population variance
print ("Variance of whole popuation is %s"
            %(statistics.pvariance(tree)))

print ("Variance of sample from population is %s "
                 % (statistics.variance(sample)))

# Print the difference in both population
# variance and sample variance
print("\n")

print("Difference in Population variance"
            "and Sample variance is % s"
        %(abs(statistics.pvariance(tree)
        - statistics.variance(sample))))
```

**输出:**

```py
Variance of the whole popuation is 0.6127751479289941
Variance of the sample from population is 0.8286277777777779 

Difference in Population variance and Sample variance is 0.21585262984878373
```

**注:**从上面的样本例子中我们可以看出，总体方差和样本方差相差不大。

**代码#5 :** 显示统计错误

## 蟒蛇 3

```py
# Python code to demonstrate StatisticsError

# importing statistics module
import statistics

# creating an empty population set
pop = ()

# will raise StatisticsError
print(statistics.pvariance(pop))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/fa112e1405f09970eeddd48214318a3c.py", line 10, in 
    print(statistics.pvariance(pop))
  File "/usr/lib/python3.5/statistics.py", line 603, in pvariance
    raise StatisticsError('pvariance requires at least one data point')
statistics.StatisticsError: pvariance requires at least one data point
```

**应用:**
总体方差的应用与样本方差非常相似，虽然总体方差的范围远大于样本方差。群体方差仅在计算整个群体的方差时使用，否则，为了计算样本的方差，优选**方差()**。群体方差是统计学和处理大量数据的一个非常重要的工具。比如，当全知均值未知(样本均值)时，方差被用作有偏估计量。