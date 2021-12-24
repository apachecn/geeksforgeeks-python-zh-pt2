# Python |重新排列正负元素

> 原文:[https://www . geesforgeks . org/python-重排-正负元素/](https://www.geeksforgeeks.org/python-rearrange-positive-and-negative-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要在列表中执行排序。可能需要执行许多不同的排序。一旦出现这种变化，就可以对列表中的元素进行排序，但请记住，正元素出现在负元素之前。让我们讨论一下执行这项任务的方法。

**方法:使用`sorted()` +λ**
该任务可以使用以上功能的组合来执行。在这种情况下，我们应用的逻辑是计算每个数字的倒数和负数，然后使用`sorted()`执行排序。反演确保较大的星等元素出现在中间，较小的星等元素出现在末端(山形排列)，而负的星等元素在负的星等元素之前出现。

```
# Python3 code to demonstrate working of
# Sort while keeping Positive elements before negatives
# using sorted() + lambda

# initialize list
test_list = [4, -8, -6, 3, -5, 8, 10, 5, -19]

# printing original list
print("The original list is : " + str(test_list))

# Sort while keeping Positive elements before negatives
# using sorted() + lambda
res = sorted(test_list, key = lambda i: 0 if i == 0 else -1 / i)

# printing result
print("Result after performing sort operation : " + str(res))
```

**Output :**

```
The original list is : [4, -8, -6, 3, -5, 8, 10, 5, -19]
Result after performing sort operation : [3, 4, 5, 8, 10, -19, -8, -6, -5]

```