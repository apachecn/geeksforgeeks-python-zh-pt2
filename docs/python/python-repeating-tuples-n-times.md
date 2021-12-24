# Python |重复元组 N 次

> 原文:[https://www . geesforgeks . org/python-repeating-元组-n-times/](https://www.geeksforgeeks.org/python-repeating-tuples-n-times/)

有时，在处理数据时，我们可能会遇到需要复制的问题，即构造元组的副本。这在计算机编程的许多领域都是重要的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`* operator`**
乘法运算符可用于构建容器的副本。这也可以扩展到元组，即使元组是不可变的。

```
# Python3 code to demonstrate working of
# Repeating tuples N times
# using * operator

# initialize tuple 
test_tup = (1, 3)

# printing original tuple 
print("The original tuple : " + str(test_tup))

# initialize N 
N = 4

# Repeating tuples N times
# using * operator
res = ((test_tup, ) * N)

# printing result
print("The duplicated tuple elements are : " + str(res))
```

**Output :**

```
The original tuple : (1, 3)
The duplicated tuple elements are : ((1, 3), (1, 3), (1, 3), (1, 3))

```