# Python |列表标准差

> 原文:[https://www . geesforgeks . org/python-标准偏差列表/](https://www.geeksforgeeks.org/python-standard-deviation-of-list/)

有时，在使用数学时，我们可能会遇到一个问题，即我们打算计算样本的标准偏差。这在竞争性编程和学校级项目中有许多应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum()` +列表理解**
这是执行这个特定任务的蛮力速记。我们可以分段处理这个问题，计算均值、方差和标准差作为方差的平方根。`sum()`是计算均值和方差的关键。列表理解用于将通用功能扩展到列表的每个元素。

```py
# Python3 code to demonstrate working of
# Standard deviation of list
# Using sum() + list comprehension

# initializing list
test_list = [4, 5, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Standard deviation of list
# Using sum() + list comprehension
mean = sum(test_list) / len(test_list)
variance = sum([((x - mean) ** 2) for x in test_list]) / len(test_list)
res = variance ** 0.5

# Printing result
print("Standard deviation of sample is : " + str(res))
```

**Output :**

```py

The original list : [4, 5, 8, 9, 10]
Standard deviation of sample is : 2.3151673805580453

```

**方法 2:使用`pstdev()`**
这个任务也可以使用`pstdev()`的内置功能来执行。该函数在内部计算样本的标准偏差。

```py
# Python3 code to demonstrate working of
# Standard deviation of list
# Using pstdev()
import statistics

# initializing list
test_list = [4, 5, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Standard deviation of list
# Using pstdev()
res = statistics.pstdev(test_list)

# Printing result
print("Standard deviation of sample is : " + str(res))
```

**Output :**

```py

The original list : [4, 5, 8, 9, 10]
Standard deviation of sample is : 2.3151673805580453

```