# Python–最小元素索引

> 原文:[https://www . geesforgeks . org/python-最小元素-indexs/](https://www.geeksforgeeks.org/python-minimum-element-indices/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们打算找到列表的最小元素的位置。这个任务很容易，讨论了很多次。但有时，我们可以有多个最小元素，从而有多个最小位置。在这种情况下，让我们讨论一种实现这一任务的速记法。

**方法:使用`min() + enumerate()` +列表理解**
在该方法中，上述功能的组合用于执行该特定任务。这分两步进行。在第一步中，我们获取最小元素，然后使用列表理解来访问列表，并使用枚举来访问对应的元素，并提取与步骤 1 中处理的最小元素相等的每个元素位置。

```py
# Python3 code to demonstrate working of
# Minimum element indices
# Using list comprehension + min() + enumerate()

# initializing list
test_list = [2, 4, 6, 8, 2, 2]

# printing list
print("The original list : " + str(test_list))

# Minimum element indices
# Using list comprehension + min() + enumerate()
temp = min(test_list)
res = [i for i, j in enumerate(test_list) if j == temp]

# Printing result
print("The Positions of minimum element : " + str(res))
```

**Output :**

```py
The original list : [2, 4, 6, 8, 2, 2]
The Positions of minimum element : [0, 4, 5]

```