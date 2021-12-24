# Python 统计模块

中的 median _ grouped()函数

> 原文:[https://www . geesforgeks . org/python-statistics-median _ group/](https://www.geeksforgeeks.org/python-statistics-median_grouped/)

来到[统计函数](https://www.geeksforgeeks.org/statistical-functions-python-set-1averages-measure-central-location/)，数据集的中值是稳健的中心趋势的度量，它受数据中异常值的影响较小。如前所述，未分组数据集的中值使用 [**中值()**](https://www.geeksforgeeks.org/python-statistics-median/) **、** [**中值 _ 高()**](https://www.geeksforgeeks.org/python-statistics-median_high/) **、** [**中值 _ 低()**](https://www.geeksforgeeks.org/median_low-python-statistics/) 函数。
Python 还提供了计算分组和连续数据函数中值的选项，这是这种健壮而方便的语言的最佳之处。**Statistics 模块下的中值 _ group()**功能，帮助从一组连续数据中计算中值。
假设将数据分组为宽度区间的区间。数组中的每个数据点都是包含真值的区间的中点。中值是在中值区间(包含中值的区间)内通过插值计算的，假设该区间内的真实值均匀分布:

```py
median = L + interval * (N / 2 - CF) / FL = lower limit of the median interval
N = total number of data points
CF = number of data points below the median interval
F = number of data points in the median interval
```

> **语法:** **中值 _ 分组(【数据集】，间隔)**
> **参数:**
> **【数据集】:**列表或元组或具有一组数值的可迭代。
> **间隔**(默认为 1)**:**决定分组数据的宽度和变化。它还将改变计算出的中值的插值。
> **Returntype :** 返回分组连续数据的中位数，计算为第 50 个<sup>百分位数。
> **异常:** **统计当可迭代传递为空或列表为空时，会引发错误**。</sup>

**代码#1 :**

## 蟒蛇 3

```py
# Python3 code to demonstrate median_grouped()

# importing median_grouped from
# the statistics module
from statistics import median_grouped

# creating an simple data-set
data1 = [15, 20, 25, 30, 35]

# printing median_grouped for the set
print("Grouped Median of the median is %s"
                %(median_grouped(data1)))
```

**输出:**

```py
Grouped Median of the median is 25.0
```

**代码#2 :** 对一系列不同数据进行中位数分组

## 蟒蛇 3

```py
# Python code to demonstrate the
# working of median_grouped()

# importing statistics module
from statistics import median_grouped

# tuple of a set of positive integers
set1 = [2, 5, 3, 4, 8, 9]

# tuple of a set of negative integers
set2 = [-6, -2, -9, -12]

# tuple of a set of positive
# and negative integers
set3 = [2, 4, 8, 9, -2, -3, -5, -6]

# Printing grouped median for
# the given set of data
print("Grouped Median of set 1 is % s" % (median_grouped(set1)))
print("Grouped Median of set 2 is % s" % (median_grouped(set2)))
print("Grouped Median of set 3 is % s" % (median_grouped(set3)))
```

**输出:**

```py
Grouped Median of set 1 is 4.5
Grouped Median of set 2 is -6.5
Grouped Median of set 3 is 1.5
```

**代码#3 :** 工作的**区间**T5】

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# interval in median_grouped() function

# importing statistics module
from statistics import median_grouped

# creating a tuple of simple data
set1 = (10, 12, 13, 12, 13, 15)

# Printing median_grouped()
# keeping default interval at 1
print("Grouped Median for Interval set as "\
      "(default) 1 is % s" %(median_grouped(set1)))

# For interval value of 2
print("Grouped Median for Interval set as "\
      "2 is % s" %(median_grouped(set1, interval = 2)))

# Now for interval value of 5
print("Grouped Median for Interval set as "\
      "5 is % s" %(median_grouped(set1, interval = 5)))
```

**输出:**

```py
Grouped Median for Interval set as (default) 1 is 12.5
Grouped Median for Interval set as 2 is 12.0
Grouped Median for Interval set as 5 is 10.5
Grouped Median for Interval set as 10 is 8.0
```

**注意:**观察一个模式，随着间隔值的增加，中间值减少。

**代码#4 :** 显示统计错误

## 蟒蛇 3

```py
# Python code to demonstrate StatisticsError

# importing the statistics module
import statistics

# creating an empty dataset
list1 = []

# Will raise StatisticsError
print(statistics.median_grouped(list1))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/0990a4a3f5206c7cd12a596cf82a1587.py", line 10, in 
    print(statistics.median_grouped(list1))
  File "/usr/lib/python3.5/statistics.py", line 431, in median_grouped
    raise StatisticsError("no median for empty data")
statistics.StatisticsError: no median for empty data
```

**应用:**
分组中位数与中位数具有相同的应用。它通常用于涉及大量数据的计算，如银行和金融。它是统计学的重要组成部分，是数据计算中最强大的工具。