# Python 统计模块中的中值 _ 高()函数

> 原文:[https://www . geesforgeks . org/python-statistics-median _ high/](https://www.geeksforgeeks.org/python-statistics-median_high/)

中值通常被称为中心位置的稳健度量，受数据中异常值的影响较小。

Python 中的**统计**模块允许三个选项来处理数据集中的中值/中间值元素，它们是`median(), median_low() and median_high()`。

*高中位数*永远是数据集中的一员。当数据点数为奇数时，返回中间值。当它为偶数时，返回两个中间值中较大的一个。让我们看看`**median_high()**`函数是如何工作的。

> **`Syntax :`** **中值 _ 高(*【数据–设置】* )**
> 
> **`Parameters :`**
> **【数据集】**:接收一个列表，或者一组可交互的数字数据。
> 
> **`Returntype :`** 返回数值数据的高中值(总是在实际数据集中)。
> 
> **`Exceptions :`** **统计当数据集为空时，会出现错误**。

**代码#1 :** 工作

```py
# Python code to demonstrate working of
# median_high() on a data-set

# importing the statistics module
import statistics

# simple list of a set of integers
set1 = [1, 3, 2, 8, 5, 4]

# Print high median of the data-set
print("High median of the data-set is %s " 
        % (statistics.median_high(set1)))
```

**输出:**

```py
High median of the data-set is 4 

```

**代码#2 :** 中值 _ 高()和中值()的工作，演示它们之间的区别。

```py
# Working of median_high() and median() to
# demonstrate the difference between them.

# importing the statistics module
import statistics

# simple list of a set of integers
set1 = [1, 3, 3, 4, 5, 7]

# Print median of the data-set

# Median value may or may not
# lie within the data-set
print("Median of the set is %s" 
      % (statistics.median(set1)))

# Print high median of the data-set
print("High Median of the set is %s " 
      % (statistics.median_high(set1)))
```

**输出:**

```py
Median of the set is 3.5
High Median of the set is 4 

```

**代码#3 :** 对不同范围的数据值使用中值 _ 高()。

```py
# Python code to demonstrate the
# working of median_high()

# importing statistics module
from statistics import median_high

# Importing fractions module as fr
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (2, 3, 4, 5, 7, 9, 11)

# tuple of a set of floating-point values
data2 = (2.4, 5.1, 6.7, 8.9)

# tuple of a set of fractional numbers
data3 = (fr(1, 2), fr(44, 12),
         fr(10, 3), fr(2, 3))

# tuple of a set of negative integers
data4 = (-5, -1, -12, -19, -3)

# tuple of set of positive
# and negative integers
data5 = (-1, -2, -3, -4, 4, 3, 2, 1)

# Print the high_median() of the given data-sets
print("High Median of data-set 1 is %s" % (median_high(data1)))
print("High Median of data-set 2 is %s" % (median_high(data2)))
print("High Median of data-set 3 is %s" % (median_high(data3)))
print("High Median of data-set 4 is %s" % (median_high(data4)))
print("High Median of data-set 5 is %s" % (median_high(data5)))
```

**输出:**

```py
High Median of data-set 1 is 5
High Median of data-set 2 is 6.7
High Median of data-set 3 is 10/3
High Median of data-set 4 is -5
High Median of data-set 5 is 1

```

**代码#4 :** 统计误差演示

```py
# Python code to demonstrate
# StatisticsError of median_high()

# importing the statistics module
from statistics import median_high

# creating an empty data-set
empty = []

# will raise StatisticsError
print(median_high(empty))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/fc2eae1616bfaa0987b261d9d40f4602.py", line 10, in 
    print(median_high(empty))
  File "/usr/lib/python3.5/statistics.py", line 398, in median_high
    raise StatisticsError("no median for empty data")
statistics.StatisticsError: no median for empty data

```

**应用:**
高中值仅在数据离散时使用，而中值更倾向于实际中值，而不是插值数据集。