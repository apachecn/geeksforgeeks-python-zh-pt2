# Python |字符串列表到列字符矩阵

> 原文:[https://www . geesforgeks . org/python-string-list-to-column-character-matrix/](https://www.geeksforgeeks.org/python-string-list-to-column-character-matrix/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要将字符串列表转换为字符矩阵，其中每行都是字符串列表列。这在数据域中可能有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解**
这是可以执行这个任务的方式之一。在本文中，我们迭代每个字符串元素，并使用索引元素构造行。

```py
# Python3 code to demonstrate working of 
# String List to Column Character Matrix
# Using list comprehension

# initializing list
test_list = ["123", "456", "789"]

# printing original list
print("The original list is : " + str(test_list))

# String List to Column Character Matrix
# Using list comprehension
res = [[sub[idx] for sub in test_list] for idx in range(len(test_list[0]))]

# printing result 
print("The Character Matrix : " + str(res)) 
```

**Output :**

```py
The original list is : ['123', '456', '789']
The Character Matrix : [['1', '4', '7'], ['2', '5', '8'], ['3', '6', '9']]

```