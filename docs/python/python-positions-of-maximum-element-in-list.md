# Python |列表中最大元素的位置

> 原文:[https://www . geesforgeks . org/python-列表中最大元素的位置/](https://www.geeksforgeeks.org/python-positions-of-maximum-element-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们打算找到列表最大元素的位置。这个任务很容易，讨论了很多次。但有时，我们可以有多个最大值元素，从而有多个最大值位置。在这种情况下，让我们讨论一种实现这一任务的速记法。

**方法:使用`max() + enumerate()` +列表理解**
在该方法中，上述功能的组合用于执行该特定任务。这分两步进行。在第一步中，我们获取最大元素，然后使用列表理解访问列表，并使用枚举提取与第一步中处理的最大元素相等的每个元素位置。

```
# Python3 code to demonstrate working of
# Positions of maximum element in list
# Using list comprehension + max() + enumerate()

# initializing list
test_list = [8, 4, 6, 8, 2, 8]

# printing list
print("The original list : " + str(test_list))

# Positions of maximum element in list
# Using list comprehension + max() + enumerate()
temp = max(test_list)
res = [i for i, j in enumerate(test_list) if j == temp]

# Printing result
print("The Positions of maximum element : " + str(res))
```

**Output :**

```

The original list : [8, 4, 6, 8, 2, 8]
The Positions of maximum element : [0, 3, 5]

```