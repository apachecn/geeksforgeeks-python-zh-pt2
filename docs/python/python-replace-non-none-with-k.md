# Python–将非无替换为 K

> 原文:[https://www . geesforgeks . org/python-replace-non-none-with-k/](https://www.geeksforgeeks.org/python-replace-non-none-with-k/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要替换所有非无的元素。这类问题可以应用于许多领域，如 web 开发和日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [2，None，None，5，"]，K = 9
> **输出** : [9，None，None，9，"]
> 
> **输入** : test_list = ["，无]，K = 10
> **输出** : ["，无]

**方法#1:使用列表理解**
这是执行这个任务的方法之一。在这种情况下，我们使用条件作为一个线性执行遍历和替换理解内部的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace Non-None with K
# Using list comprehension

# initializing list
test_list = [59, 236, None, 3, '']

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 'Gfg'

# Replace Non-None with K
# Using list comprehension
res = [K if ele else ele for ele in test_list]

# printing result 
print("List after replacement : " + str(res))
```

**Output :**

```
The original list : [59, 236, None, 3, '']
List after replacement : ['Gfg', 'Gfg', None, 'Gfg', '']

```

**方法 2:使用`map() + lambda()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行将 lambda 逻辑扩展到整个列表的任务，并执行替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace Non-None with K
# Using map() + lambda()

# initializing list
test_list = [59, 236, None, 3, '']

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 'Gfg'

# Replace Non-None with K
# Using map() + lambda()
res = list(map(lambda ele: K if ele else ele, test_list))

# printing result 
print("List after replacement : " + str(res))
```

**Output :**

```
The original list : [59, 236, None, 3, '']
List after replacement : ['Gfg', 'Gfg', None, 'Gfg', '']

```