# Python |删除元组中的重复列表(保留顺序)

> 原文:[https://www . geesforgeks . org/python-remove-replicate-list-in-tuples-preserving-order/](https://www.geeksforgeeks.org/python-remove-duplicate-lists-in-tuples-preserving-order/)

有时，在处理记录时，我们可能会遇到需要删除重复记录的问题。这种问题在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。
**方法#1:使用列表理解+集合()**
在该方法中，我们对每个出现的列表进行测试，并将其添加到集合中，以避免其重复出现，然后将其添加到新维护的唯一元组中，删除重复项。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove duplicate lists in tuples(Preserving Order)
# Using list comprehension + set()

# Initializing tuple
test_tup = ([4, 7, 8], [1, 2, 3], [4, 7, 8], [9, 10, 11], [1, 2, 3])

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Remove duplicate lists in tuples(Preserving Order)
# Using list comprehension + set()
temp = set()
res = [ele for ele in test_tup if not(tuple(ele) in temp or temp.add(tuple(ele)))]

# printing result
print("The unique lists tuple is : " + str(res))
```

**Output : **

```py
The original tuple is : ([4, 7, 8], [1, 2, 3], [4, 7, 8], [9, 10, 11], [1, 2, 3])
The unique lists tuple is : [[4, 7, 8], [1, 2, 3], [9, 10, 11]]
```

**方法#2:使用 ordereddct()+tuple()**
上述函数的组合也可以用来执行这个特定的任务。在本文中，我们将元组转换为 OrderedDict()，它会自动移除重复的元素，然后使用 tuple()构造一个新的元组列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove duplicate lists in tuples(Preserving Order)
# Using OrderedDict() + tuple()
from collections import OrderedDict

# Initializing tuple
test_tup = ([4, 7, 8], [1, 2, 3], [4, 7, 8], [9, 10, 11], [1, 2, 3])

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Remove duplicate lists in tuples(Preserving Order)
# Using OrderedDict() + tuple()
res = list(OrderedDict((tuple(x), x) for x in test_tup).values())

# printing result
print("The unique lists tuple is : " + str(res))
```

**Output : **

```py
The original tuple is : ([4, 7, 8], [1, 2, 3], [4, 7, 8], [9, 10, 11], [1, 2, 3])
The unique lists tuple is : [[4, 7, 8], [1, 2, 3], [9, 10, 11]]
```