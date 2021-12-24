# Python |元组列表中产品对的最大数量

> 原文:[https://www . geesforgeks . org/python-元组列表中产品对的最大数量/](https://www.geeksforgeeks.org/python-maximum-of-product-pairs-in-tuple-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要在列表中的可用对之间找到最大乘积。这可以应用于数学领域的许多问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`max()` +列表理解**
该功能的组合可用于执行该任务。在本文中，我们计算所有对的乘积，然后使用 max()返回它的最大值。

```py
# Python3 code to demonstrate working of
# Maximum of Product Pairs in Tuple List
# Using list comprehension + max()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list 
print("The original list : " + str(test_list))

# Maximum of Product Pairs in Tuple List
# Using list comprehension + max()
temp = [abs(b * a) for a, b in test_list]
res = max(temp)

# printing result
print("Maximum product among pairs : " + str(res))
```

**Output :**

```py
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Maximum product among pairs : 30

```