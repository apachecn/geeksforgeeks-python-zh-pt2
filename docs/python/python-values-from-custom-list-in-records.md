# Python–记录中自定义列表的值

> 原文:[https://www . geesforgeks . org/python-值-来自自定义记录列表/](https://www.geeksforgeeks.org/python-values-from-custom-list-in-records/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要从列表字典记录中的自定义列表中提取所有值。这个问题可以应用于网络开发和学校编程等领域。让我们讨论执行这项任务的某些方法。

> **输入**:
> test _ list =[{ ' name ':' Gfg '，' id' : 1，' Score' : 3}，{'name' : 'is '，' id' : 4，' Score' : 10}，
> {'name' : 'Best '，' Score ':12 }]
> get _ list =[' name ']
> **输出**:[' Gfg ']，['is']，['Best']
> 
> **输入**:
> test _ list =[{ ' name ':' Gfg '，' id' : 1，' Score' : 3}，{'name' : 'is '，' id' : 4，' Score' : 10}，
> {'name' : 'Best '，' Score ':12 }]
> get _ list =[' Serial ']
> **输出**:[[无]，[无]，[无]]

**方法#1:使用列表理解+ `get()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用列表理解执行遍历每个字典的任务，get()用于获取字典值并处理非当前值。

```
# Python3 code to demonstrate working of 
# Values from custom List in Records
# Using list comprehension + get()

# initializing list
test_list = [{'name' : 'Gfg', 'id' : 1, 'Score' : 3},
             {'name' : 'is', 'id' : 4, 'Score' : 10},
             {'name' : 'Best', 'Score' : 12}]

# printing original list 
print("The original list : " + str(test_list))

# initializing Get list 
get_list = ['name', 'id']

# Values from custom List in Records
# Using list comprehension + get()
res = [list(idx.get(sub) for sub in get_list) for idx in test_list]

# printing result 
print("All extracted values : " + str(res))
```

**Output :**

```
The original list : [{'name': 'Gfg', 'id': 1, 'Score': 3}, {'name': 'is', 'id': 4, 'Score': 10}, {'name': 'Best', 'Score': 12}]
All extracted values : [['Gfg', 1], ['is', 4], ['Best', None]]

```

**方法 2:使用列表理解+ `itemgetter() + intersection()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 itemgetter()和交集()来获取检查目标列表和参数列表的值。无法处理不存在的钥匙。

```
# Python3 code to demonstrate working of 
# Values from custom List in Records
# Using list comprehension + itemgetter() + intersection()
from operator import itemgetter

# initializing list
test_list = [{'name' : 'Gfg', 'id' : 1, 'Score' : 3},
             {'name' : 'is', 'id' : 4, 'Score' : 10}]

# printing original list 
print("The original list : " + str(test_list))

# initializing Get list 
get_list = ['name', 'id']

# Values from custom List in Records
# Using list comprehension + itemgetter() + intersection()
res = [list(itemgetter(*set(get_list).intersection(idx))(idx)) for idx in test_list]

# printing result 
print("All extracted values : " + str(res))
```

**Output :**

```
The original list : [{'name': 'Gfg', 'id': 1, 'Score': 3}, {'name': 'is', 'id': 4, 'Score': 10}]
All extracted values : [[1, 'Gfg'], [4, 'is']]

```