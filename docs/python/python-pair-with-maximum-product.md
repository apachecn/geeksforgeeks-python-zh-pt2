# Python–与最大乘积配对

> 原文:[https://www . geesforgeks . org/python-与最大产品配对/](https://www.geeksforgeeks.org/python-pair-with-maximum-product/)

有时，我们需要找到获得产生最大乘积的对的具体问题，这可以通过在排序后获得初始的两个元素来计算。但是在某些情况下，我们不需要改变列表的顺序，在不使用额外空间的情况下在相似的列表中执行一些操作。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+`max() + combination()`+λ**
这个特殊的任务可以使用上述函数的组合来执行，其中我们使用列表理解来绑定所有功能和 max 函数来获得最大产品，组合函数在内部查找所有产品，λ函数用于计算产品。

```py
# Python3 code to demonstrate
# Pair with Maximum product
# using list comprehension + max() + combinations() + lambda
from itertools import combinations

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + max() + combinations() + lambda
# Pair with Maximum product
res = max(combinations(test_list, 2), key = lambda sub: abs(sub[0] * sub[1]))

# print result
print("The maximum product pair is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The maximum product pair is : (7, 9)

```