# Python–矩阵中奇数或偶数元素组合和

> 原文:[https://www . geesforgeks . org/python-奇数或偶数元素-组合-矩阵求和/](https://www.geeksforgeeks.org/python-odd-or-even-elements-combinations-summations-in-matrix/)

有时候，在使用 Python 时，我们可能会遇到这样的问题，我们需要提取所有可能的元素总和，从矩阵的每一行中提取一个，要么是所有奇数元素，要么是偶数元素。这是一个非常特殊的问题，但可以在某些领域得到应用。让我们讨论执行这项任务的特定方式。

**方法:使用生成器表达式+ `lambda + sum() + map() + all()`**
以上方法的组合可以用来执行这个任务。在这种情况下，我们使用 all() +生成器表达式来执行提取所有奇数或偶数对的任务。求和的构造任务是使用 sum()和 lambda 函数完成的。

```py
# Python3 code to demonstrate working of 
# Odd or Even elements combinations Summations in Matrix
# Using generator expression + lambda + sum() + map() + all()
from itertools import product

# initializing list
test_list = [[1, 5, 6], [7, 2, 4], [8, 9, 3]]

# printing original list
print("The original list is : " + str(test_list))

# Odd or Even elements combinations Summations in Matrix
# Using generator expression + lambda + sum() + map() + all()
temp1 = product(*test_list)
temp2 = (sub for sub in temp1 if all(ele % 2 == 0 for ele in sub)
        or all(ele % 2 == 1 for ele in sub))
res = {sum(map(lambda idx : idx, ele)) : ele for ele in temp2}

# printing result 
print("The all possible sums are : " + str(res)) 
```

**Output :**

> 原始列表为:[[1，5，6]，[7，2，4]，[8，9，3]]
> 所有可能的和为:{16: (6，2，8)，17: (1，7，9)，18: (6，4，8)，21: (5，7，9)，11: (1，7，3)，15: (5，7，3)}