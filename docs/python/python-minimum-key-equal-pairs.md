# Python |最小键相等对

> 原文:[https://www . geesforgeks . org/python-最小密钥-相等对/](https://www.geeksforgeeks.org/python-minimum-key-equal-pairs/)

有时候，在使用 Python 时，我们可能会遇到一个问题，需要获取所有记录。这些数据可以有相似的值，我们需要找到最小键值对。处理数据时可能会出现这种问题。让我们讨论一下完成这项任务的某些方法。

**方法一:使用`min() + groupby() + itemgetter()` +列表理解**

上述功能的组合可用于执行该特定任务。在本文中，我们首先使用 groupby()和 itemgetter()对相似的有值元素进行分组，然后使用 min()提取其中的最小值，并使用列表理解在列表中累加结果。

```
# Python3 code to demonstrate working of
# Minimum key equal pairs
# using min() + groupby() + itemgetter() + list comprehension
from operator import itemgetter
from itertools import groupby

# initialize list
test_list = [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]

# printing original list
print("The original list : " + str(test_list))

# Minimum key equal pairs
# using min() + groupby() + itemgetter() + list comprehension
res = [min(values) for key, values in groupby(test_list, key = itemgetter(1))]

# printing result
print("Minimum key equal pairs : " + str(res))
```

**Output :**

```
The original list : [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]
Minimum key equal pairs : [(2, 3), (3, 10), (5, 6)]

```

**方法二:使用`setdefault() + items()` +循环+列表理解**

以上功能的组合也可以实现这个任务。在本例中，我们将列表元组键值对转换为字典，并使用 setdefault()指定默认值。使用列表理解计算最终结果。

```
# Python3 code to demonstrate working of
# Minimum key equal pairs
# using setdefault() + items() + loop + list comprehension

# initialize list
test_list = [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]

# printing original list
print("The original list : " + str(test_list))

# Minimum key equal pairs
# using setdefault() + items() + loop + list comprehension
temp = {}
for val, key in test_list:
    if val < temp.setdefault(key, val):
        temp[key] = val
res = [(val, key) for key, val in temp.items()]

# printing result
print("Minimum key equal pairs : " + str(res))
```

**Output :**

```
The original list : [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]
Minimum key equal pairs : [(2, 3), (3, 10), (5, 6)]

```