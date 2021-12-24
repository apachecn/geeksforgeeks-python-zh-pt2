# Python | N 元素增量元组

> 原文:[https://www . geesforgeks . org/python-n-element-incremental-元组/](https://www.geeksforgeeks.org/python-n-element-incremental-tuples/)

有时，在处理数据时，我们会遇到一个问题，即我们需要收集一个数据，该数据是递增元素元组序列的形式，每个元组包含 N 次元素。让我们讨论执行这项任务的某些方法。

**方法#1:使用生成器表达式+ `tuple()`**
以上功能的组合可用于执行此任务。在这种情况下，我们需要使用生成器表达式迭代 N，并使用元组()构造元组。

```
# Python3 code to demonstrate working of
# N element incremental tuples
# Using generator expression + tuple

# initialize N 
N = 3 

# printing N
print("Number of times to repeat : " + str(N))

# N element incremental tuples
# Using generator expression + tuple
res = tuple((ele, ) * N for ele in range(1, 6))

# printing result
print("Tuple sequence : " + str(res))
```

**Output :**

```
Number of times to repeat : 3
Tuple sequence : ((1, 1, 1), (2, 2, 2), (3, 3, 3), (4, 4, 4), (5, 5, 5))

```