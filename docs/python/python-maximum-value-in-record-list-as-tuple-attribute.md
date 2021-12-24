# Python–记录列表中作为元组属性的最大值

> 原文:[https://www . geesforgeks . org/python-记录中最大值列表作为元组属性/](https://www.geeksforgeeks.org/python-maximum-value-in-record-list-as-tuple-attribute/)

很多时候，在处理任何语言的容器时，我们都会遇到不同形式的元组列表，元组本身有时可以有比本机数据类型更多的数据类型，并且可以有列表作为它们的属性。本文将列表的最大值作为元组属性。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `max()`**
这个特殊的问题可以通过使用列表理解结合 max 函数来解决，其中我们使用 max 函数来找到列表的 max 作为元组属性，并使用列表理解来迭代列表。

```
# Python3 code to demonstrate
# Records element list Maximum
# using list comprehension + max()

# initializing list
test_list = [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + max()
# Records element list Maximum
res = [(key, max(lst)) for key, lst in test_list]

# print result
print("The list tuple attribute maximum is : " + str(res))
```

**Output :**

```
The original list : [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]
The list tuple attribute maximum is : [('key1', 5), ('key2', 4), ('key3', 9)]

```