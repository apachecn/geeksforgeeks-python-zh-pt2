# Python–将长度列为记录属性

> 原文:[https://www . geesforgeks . org/python-list-length-as-record-attribute/](https://www.geeksforgeeks.org/python-list-lengths-as-record-attribute/)

很多时候，在处理任何语言的容器时，我们都会遇到不同形式的元组列表，元组本身有时可以有比本机数据类型更多的数据类型，并且可以有列表作为它们的属性。本文讨论作为元组属性的列表长度。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `len()`**
这个特殊的问题可以通过使用列表理解结合 len 函数来解决，在 len 函数中，我们使用 len 函数来找到列表的 len 作为元组属性，并使用列表理解来迭代列表。

```
# Python3 code to demonstrate
# List lengths as record attribute
# using list comprehension + len()

# initializing list
test_list = [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + len()
# List lengths as record attribute
res = [(key, len(lst)) for key, lst in test_list]

# print result
print("The list tuple attribute lengths is : " + str(res))
```

**Output :**

```
The original list : [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]
The list tuple attribute lengths is : [('key1', 3), ('key2', 3), ('key3', 2)]

```