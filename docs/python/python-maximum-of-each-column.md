# Python–每列的最大值

> 原文:[https://www . geesforgeks . org/python-每列最大数量/](https://www.geeksforgeeks.org/python-maximum-of-each-column/)

有时，我们会遇到这样的问题，我们需要找到矩阵中每一列的最大值，即列表中每个索引的最大值。这种问题在竞争性编程中很常见，也很有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`max() + list comprehension + zip()`**
需要结合以上方法来解决这个特殊问题。max 函数用于获取所需的最大值，zip 函数提供相似索引的组合，然后使用列表理解创建列表。

```
# Python3 code to demonstrate
# Maximum of each Column
# using max() + list comprehension + zip()

# initializing list
test_list = [[3, 7, 6], [1, 3, 5], [9, 3, 2]]

# printing original list
print("The original list : " + str(test_list))

# using max() + list comprehension + zip()
# Maximum of each Column
res = [max(idx) for idx in zip(*test_list)]

# print result
print("The Maximum of each index list is : " + str(res))
```

**Output :**

```
The original list : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
The Maximum of each index list is : [9, 7, 6]

```