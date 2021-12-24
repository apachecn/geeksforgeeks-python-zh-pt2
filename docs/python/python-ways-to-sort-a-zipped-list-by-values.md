# Python |按值对压缩列表进行排序的方法

> 原文:[https://www . geesforgeks . org/python-按值对压缩列表进行排序的方法/](https://www.geeksforgeeks.org/python-ways-to-sort-a-zipped-list-by-values/)

压缩列表是指将几个列表映射在一起，形成一个可以作为一个整体使用的列表。在 Python 中`Zip()`函数用于映射不同的列表。

让我们讨论几个方法来演示这个问题。

**方法#1:** 使用λ和排序

```py
# Python code to demonstrate
# sort zipped list by values
# using lambda and sorted

# Declaring initial lists
list1 = ['geeks', 'for', 'Geeks']
list2 = [3, 2, 1]
zipped = zip(list1, list2)

# Converting to list
zipped = list(zipped)

# Printing zipped list
print("Initial zipped list - ", str(zipped))

# Using sorted and lambda
res = sorted(zipped, key = lambda x: x[1])

# printing result
print("final list - ", str(res))
```

**Output:**

```py
Initial zipped list -  [('geeks', 3), ('for', 2), ('Geeks', 1)]
final list -  [('Geeks', 1), ('for', 2), ('geeks', 3)]

```

**方法 2:** 使用运算符和排序

```py
# Python code to demonstrate
# sort zipped list by values
# using operator and sorted

import operator
# Declaring initial lists
list1 = ['akshat', 'Manjeet', 'nikhil']
list2 = [3, 2, 1]
zipped = zip(list1, list2)

# Converting to list
zipped = list(zipped)

# Printing zipped list
print("Initial zipped list - ", str(zipped))

# Using sorted and operator
res = sorted(zipped, key = operator.itemgetter(1))

# printing result
print("final list - ", str(res))
```

**Output:**

```py
Initial zipped list -  [('akshat', 3), ('Manjeet', 2), ('nikhil', 1)]
final list -  [('nikhil', 1), ('Manjeet', 2), ('akshat', 3)]

```