# Python–按字典值排序列表

> 原文:[https://www . geesforgeks . org/python-按字典排序-列表-值/](https://www.geeksforgeeks.org/python-sort-list-by-dictionary-values/)

有时在使用 Python 字典时，我们可能会遇到这样的问题，即需要根据字典中的相应值执行一种列表排序。这可以应用于许多领域，包括数据和网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sorted() + key + lambda`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序任务。lambda 函数用于获取键值。

```py
# Python3 code to demonstrate working of 
# Sort List by Dictionary values
# Using sorted() + key + lambda

# initializing list
test_list = ['gfg', 'is', 'best']

# initializing Dictionary
test_dict = {'gfg' : 56, 'is' : 12, 'best' : 76}

# printing original list
print("The original list is : " + str(test_list))

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sort List by Dictionary values
# Using sorted() + key + lambda
res = sorted(test_list, key = lambda ele: test_dict[ele])

# printing result 
print("The list after sorting : " + str(res)) 
```

**Output :**

```py
The original list is : ['gfg', 'is', 'best']
The original dictionary is : {'best': 76, 'gfg': 56, 'is': 12}
The list after sorting : ['is', 'gfg', 'best']

```