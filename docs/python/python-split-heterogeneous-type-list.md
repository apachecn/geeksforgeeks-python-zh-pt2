# Python–拆分异构类型列表

> 原文:[https://www . geesforgeks . org/python-split-异类-类型-列表/](https://www.geeksforgeeks.org/python-split-heterogeneous-type-list/)

有时，我们可能使用许多数据类型，在这些情况下，我们可能会遇到一个问题，即我们收到的列表可能包含来自不同数据类型的元素。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ isinstance()**
以上两个功能的组合可以用来执行这个任务。在本文中，我们只是使用不同的列表理解提取相似的元素类型，并使用 isinstance()检测类型。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Split heterogeneous type list
# using list comprehension + isinstance

# initialize list
test_list = ['gfg', 1, 2, 'is', 'best']

# printing original list
print("The original list : " + str(test_list))

# Split heterogeneous type list
# using list comprehension + isinstance
res_str = [ele for ele in test_list if isinstance(ele, str)]
res_int = [ele for ele in test_list if isinstance(ele, int)]

# printing result
print("Integer list : " + str(res_int))
print("String list : " + str(res_str))
```

**Output : **

```py
The original list : ['gfg', 1, 2, 'is', 'best']
Integer list : [1, 2]
String list : ['gfg', 'is', 'best']
```

**方法 2:使用 defaultdict() + loop**
这是解决这个问题的又一种方法。在本文中，我们将列表初始化为 defaultdict()的数据类型，并循环遍历每个元素，将每个数据类型列表保存在 defaultdict 中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Split heterogeneous type list
# using defaultdict() + loop
from collections import defaultdict

# initialize list
test_list = ['gfg', 1, 2, 'is', 'best']

# printing original list
print("The original list : " + str(test_list))

# Split heterogeneous type list
# using defaultdict() + loop
res = defaultdict(list)
for ele in test_list:
   res[type(ele)].append(ele)

# printing result
print("Integer list : " + str(res[int]))
print("String list : " + str(res[str]))
```

**Output : **

```py
The original list : ['gfg', 1, 2, 'is', 'best']
Integer list : [1, 2]
String list : ['gfg', 'is', 'best']
```