# Python 中的调和 _ 均值()

> 原文:[https://www . geesforgeks . org/python-statistics-harmonic _ mean/](https://www.geeksforgeeks.org/python-statistics-harmonic_mean/)

调和平均值(也称为相反平均值)是几种平均值之一，尤其是毕达哥拉斯平均值之一。通常用于需要平均费率的情况。调和平均值也是给定一组观测值倒数的算术平均值的倒数。

例如，谐波平均值 1、4 和 4 可以计算为:

通过使用统计模块中的**调和平均值()**函数，调和平均值可以合并到 Python3 中。

> **语法:** **调和 _ 均值(【数据集】)**
> **参数:**
> **【数据集】**:是实数的列表或元组或迭代器。
> **Returntype :** 返回给定数据集的调和平均值。
> **错误和异常:**
> **统计当传递空数据集或数据集包含负值时出现错误**。对于非数值类型值的数据集，
> **类型错误**。

**注意:**谐波平均值仅使用列表、集合或任何序列中的正值计算。

**代码#1 :**

## 蟒蛇 3

```py
# Python3 code to demonstrate the
# working of harmonic_mean() function

# Import statistics module
import statistics

# list of positive real valued numbers
data = [1, 3, 5, 7, 9]

# using harmonic mean function to calculate
# the harmonic mean of the given data-set
print("Harmonic Mean is % s " % (statistics.harmonic_mean(data)))
```

**输出:**

```py
Harmonic Mean is 2.797513321492007 
```

**代码#2 :**

## 蟒蛇 3

```py
# Python3 program to demonstrate harmonic_mean()
# function from the statistics module

# Importing the statistics module
from statistics import harmonic_mean

# Importing fractions module as fr
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (2, 3, 4, 5, 7, 9, 11)

# tuple of a set of floating-point values
data2 = (2.4, 5.1, 6.7, 8.9)

# tuple of a set of fractional numbers
data3 = (fr(1, 2), fr(44, 12), fr(10, 3), fr(2, 3))

# dictionary of a set of values
# Only the keys are taken in
# consideration by harmonic_mean()
data4 = {1: "one", 2: "two", 3: "three"}

# Printing the harmonic mean of above datasets
print("Harmonic Mean of data set 1 is % s"
                 % (harmonic_mean(data1)))

print("Harmonic Mean of data set 2 is % s"
                 % (harmonic_mean(data2)))

print("Harmonic Mean of data set 3 is % s"
                 % (harmonic_mean(data3)))

print("Harmonic Mean of data set 4 is % s"
                % (harmonic_mean(data4)))
```

**输出:**

```py
Harmonic Mean of data set 1 is 4.299197943900386
Harmonic Mean of data set 2 is 4.574783168721765
Harmonic Mean of data set 4 is 55/56
Harmonic Mean of data set 5 is 1.6363636363636365
```

**代码#3 :** 显示统计错误

## 蟒蛇 3

```py
# Python code to demonstrate StatisticsError
# while using harmonic_mean()

# importing statistics module
import statistics

# data-set of numbers containing
# a negative number
dat1 = [1, -1]

# Statistics Error is raised when the
# data-set passed as parameter is
# empty or contain a negative value
print(statistics.harmonic_mean(dat1))
```

**输出:**

```py
Traceback (most recent call last):
  File "C:/Users/Souveek/PycharmProjects/Test.py", line 12, in 
    print(statistics.harmonic_mean((1, -1)))
  File "C:\Users\Souveek\AppData\Local\Programs\Python\Python36-32\Lib\statistics.py", line 356, in harmonic_mean
    T, total, count = _sum(1/x for x in _fail_neg(data, errmsg))
  File "C:\Users\Souveek\AppData\Local\Programs\Python\Python36-32\Lib\statistics.py", line 148, in _sum
    for n, d in map(_exact_ratio, values):
  File "C:\Users\Souveek\AppData\Local\Programs\Python\Python36-32\Lib\statistics.py", line 356, in 
    T, total, count = _sum(1/x for x in _fail_neg(data, errmsg))
  File "C:\Users\Souveek\AppData\Local\Programs\Python\Python36-32\Lib\statistics.py", line 285, in _fail_neg
    raise StatisticsError(errmsg)
statistics.StatisticsError: harmonic mean does not support negative values
```

**注意:**以下代码可能不会在联机 IDEs 上运行，因为在 Python3.6

**中新引入了 harmonic_mean()函数应用:**
Harmonic Mean 是金融中众多重要工具之一(统计下)。加权调和平均值是平均倍数的优选方法，例如市盈率，其中价格在分子中。它也用于算术平均值高估所需结果的地方的计算。