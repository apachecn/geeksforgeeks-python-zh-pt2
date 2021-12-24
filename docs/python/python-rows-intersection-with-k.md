# Python–与 K 相交的行

> 原文:[https://www . geeksforgeeks . org/python-row-intersection-with-k/](https://www.geeksforgeeks.org/python-rows-intersection-with-k/)

有时在使用 Python Matrix 时，我们会遇到一个问题，即我们需要提取与其他矩阵匹配的所有行，而其他矩阵有一个特定的元素。这种问题可能发生在数据域中，因为矩阵是许多问题的输入数据类型。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list1 = [[5，6，7]，[7，6，6]，[5，7，10]]
> test_list2 = [[5，6，7]，[7，6，8]，[5，7，10]]
> K = 7
> **输出** : 2
> **输入** :
> test_list1 = [[6，7]，[6]，[5]

**方法#1:使用 sum() +生成器表达式**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 sum()执行计数匹配的任务，使用 generator 表达式执行比较的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rows intersection with K
# Using sum() + generator expression

# initializing lists
test_list1 = [[5, 6, 7], [7, 6, 6], [5, 7, 10]]
test_list2 = [[5, 6, 7], [7, 6, 8], [5, 7, 10]]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 5

# Rows intersection with K
# Using sum() + generator expression
res = sum(sum(a == b for b in test_list2) for a in test_list1 if K in a)

# printing result
print("The matched rows : " + str(res))
```

**Output : **

```py
The original list 1 is : [[5, 6, 7], [7, 6, 6], [5, 7, 10]]
The original list 2 is : [[5, 6, 7], [7, 6, 8], [5, 7, 10]]
The matched rows : 2
```

**方法 2:使用 Counter() + sum() +列表理解**
以上功能的组合可以作为解决这个问题的替代方案。在本例中，我们使用 sum()执行求和，Counter()用于映射列表 2 中的行，以便在计数频率求和时与列表 1 进行比较。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rows intersection with K
# Using Counter() + sum() + list comprehension
from collections import Counter

# initializing lists
test_list1 = [[5, 6, 7], [7, 6, 6], [5, 7, 10]]
test_list2 = [[5, 6, 7], [7, 6, 8], [5, 7, 10]]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 5

# Rows intersection with K
# Using Counter() + sum() + list comprehension
temp = Counter(tuple(b) for b in test_list2)
res = sum(temp[tuple(a)] for a in test_list1 if K in a)

# printing result
print("The matched rows : " + str(res))
```

**Output : **

```py
The original list 1 is : [[5, 6, 7], [7, 6, 6], [5, 7, 10]]
The original list 2 is : [[5, 6, 7], [7, 6, 8], [5, 7, 10]]
The matched rows : 2
```