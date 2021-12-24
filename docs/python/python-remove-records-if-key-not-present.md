# Python–如果键不存在，则删除记录

> 原文:[https://www . geesforgeks . org/python-remove-records-if-key-not-present/](https://www.geeksforgeeks.org/python-remove-records-if-key-not-present/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要删除所有不存在特定键的字典。这类问题可以应用于许多领域，如日常编程和数据领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'Gfg' : 1，' Best' : 3}，{'Gfg' : 3，' Best' : 5}，{'Best' : 3}]，K = 'Best'
> **输出** : [{'Gfg' : 1，' Best' : 3}，{'Gfg' : 3，' Best' : 5}，{'Best' : 3}]
> 
> **输入** : test_list = [{'Gfg' : 1，' Best' : 3}，{'Gfg' : 3，' Best' : 5}，{'Best' : 3}]，K = 'good'
> **输出** : []

**方法#1:使用列表理解**
这是执行这个任务的方法之一。在本文中，我们使用列表理解和条件语句来迭代和测试关键存在。

```py
# Python3 code to demonstrate working of 
# Remove records if Key not present
# Using list comprehension

# initializing list
test_list = [{'Gfg' : 1, 'Best' : 3},
             {'Gfg' : 3, 'Best' : 5}, 
             {'Best' : 3}]

# printing original list 
print("The original list : " + str(test_list))

# initializing K Key
K = 'Gfg'

# Remove records if Key not present
# Using list comprehension
res = [ele for ele in test_list if K in ele]

# printing result 
print("List after filteration : " + str(res))
```

**Output :**

```py
The original list : [{'Gfg': 1, 'Best': 3}, {'Gfg': 3, 'Best': 5}, {'Best': 3}]
List after filteration : [{'Gfg': 1, 'Best': 3}, {'Gfg': 3, 'Best': 5}]

```

**方法 2:使用列表理解+ `keys()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 key()执行提取所有键的任务，减少了检入项的开销。

```py
# Python3 code to demonstrate working of 
# Remove records if Key not present
# Using list comprehension + keys()

# initializing list
test_list = [{'Gfg' : 1, 'Best' : 3},
             {'Gfg' : 3, 'Best' : 5}, 
             {'Best' : 3}]

# printing original list 
print("The original list : " + str(test_list))

# initializing K Key
K = 'Gfg'

# Remove records if Key not present
# Using list comprehension + keys()
res = [ele for ele in test_list if K in ele.keys()]

# printing result 
print("List after filteration : " + str(res))
```

**Output :**

```py
The original list : [{'Gfg': 1, 'Best': 3}, {'Gfg': 3, 'Best': 5}, {'Best': 3}]
List after filteration : [{'Gfg': 1, 'Best': 3}, {'Gfg': 3, 'Best': 5}]

```