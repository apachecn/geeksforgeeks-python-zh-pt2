# Python–列表中的最小产品对

> 原文:[https://www . geesforgeks . org/python-最小产品对列表/](https://www.geeksforgeeks.org/python-minimum-product-pair-in-list/)

有时，我们需要找到获得产生最小乘积的对的具体问题，这可以通过排序并获得列表的第一个和第二个元素来解决。但是在某些情况下，我们不需要改变列表的顺序，在不使用额外空间的情况下在相似的列表中执行一些操作。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `min() + combination()` + lambda**
这个特定的任务可以使用上述函数的组合来执行，其中我们使用列表理解来绑定所有的功能和 min 函数来获得最小乘积，组合函数在内部找到所有的乘积，lambda 函数用于计算乘积。

```py
# Python3 code to demonstrate
# Minimum Product Pair in List
# using list comprehension + min() + combinations() + lambda
from itertools import combinations

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + min() + combinations() + lambda
# Minimum Product Pair in List
res = min(combinations(test_list, 2), key = lambda sub: sub[0] * sub[1])

# print result
print("The minimum product pair is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The minimum product pair is : (1, 1)

```