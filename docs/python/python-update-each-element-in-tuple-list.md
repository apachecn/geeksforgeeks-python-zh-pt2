# Python |更新元组列表中的每个元素

> 原文:[https://www . geesforgeks . org/python-update-元组列表中的每个元素/](https://www.geeksforgeeks.org/python-update-each-element-in-tuple-list/)

有时，在处理数据时，我们会遇到一个问题，需要对元组执行更新操作。这可以有跨许多领域的应用，如网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是可以应用于执行该任务的蛮力函数的简写。在这种情况下，我们迭代每个元组的每个元素来执行数据的批量更新。

```py
# Python3 code to demonstrate working of
# Update each element in tuple list
# Using list comprehension

# initialize list
test_list = [(1, 3, 4), (2, 4, 6), (3, 8, 1)]

# printing original list 
print("The original list : " + str(test_list))

# initialize add element
add_ele = 4

# Update each element in tuple list
# Using list comprehension
res = [tuple(j + add_ele for j in sub ) for sub in test_list]

# printing result
print("List after bulk update : " + str(res))
```

**Output :**

```py
The original list : [(1, 3, 4), (2, 4, 6), (3, 8, 1)]
List after bulk update : [(5, 7, 8), (6, 8, 10), (7, 12, 5)]

```