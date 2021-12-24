# Python | Pair 产品组合

> 原文:[https://www . geesforgeks . org/python-pair-product-combinations/](https://www.geeksforgeeks.org/python-pair-product-combinations/)

有时，在处理数据时，我们会遇到一个问题，即我们需要在列表中的所有元组之间执行元组乘法。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`combinations()` +列表理解**
这个问题可以通过以上功能的组合来解决。在这种情况下，我们使用组合()来生成元组中所有可能的组合，并使用列表理解来馈送产品逻辑。

```py
# Python3 code to demonstrate working of
# Pair Product combinations
# Using list comprehension + combinations
from itertools import combinations

# initialize list 
test_list = [(2, 4), (6, 7), (5, 1), (6, 10)]

# printing original list 
print("The original list : " + str(test_list))

# Pair Product combinations
# Using list comprehension + combinations
res = [(b1 * a1, b2 * a2) for (a1, a2), (b1, b2) in combinations(test_list, 2)] 

# printing result
print("The Product pair combinations are : " + str(res))
```

**Output :**

```py
The original list : [(2, 4), (6, 7), (5, 1), (6, 10)]
The Product pair combinations are : [(12, 28), (10, 4), (12, 40), (30, 7), (36, 70), (30, 10)]

```