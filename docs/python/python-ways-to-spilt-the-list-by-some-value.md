# Python |按值拆分列表的方法

> 原文:[https://www . geesforgeks . org/python-按某些值拆分列表的方法/](https://www.geeksforgeeks.org/python-ways-to-spilt-the-list-by-some-value/)

给定一个列表(可能包含字符串或数字)，任务是将列表按某个值分成两个列表。
方法很简单。将列表的前半部分按给定值拆分，后半部分按相同值拆分。根据需求，此操作可能有多种变化，例如在拆分值后的后半部分删除第一个/某些元素等。让我们看看完成这项任务的不同方法。

**方法#1:使用列表索引**

## 蟒蛇 3

```py
# Python code to split the list
# by some value into two lists.

# List initialisation
list = ['Geeks', 'forgeeks', 'is a', 'portal', 'for Geeks']

# Splitting list into first half
first_list = list[:list.index('forgeeks')]

# Splitting list into second half
second_list = list[list.index('forgeeks')+1:]

# Printing first list
print(first_list)

# Printing second list
print(second_list)
```

**Output:** 

```py
['Geeks']
['is a', 'portal', 'for Geeks']
```

**方法 2:使用 dropwhile 并设置**

## 蟒蛇 3

```py
# Python code to split the list
# by some value into two lists.

# Importing
from itertools import dropwhile

# List initialisation
lst = ['Geeks', 'forgeeks', 'is a', 'portal', 'for Geeks']

# Using dropwhile to split into second list
second_list = list(dropwhile(lambda x: x != 'forgeeks', lst))[1:]

# Using set to get difference between two lists
first_list = set(lst)-set(second_list)

# removing 'split' string
first_list.remove('forgeeks')

# converting to list
first_list = list(first_list)

# Printing first list
print(first_list)

# Printing second list
print(second_list)
```

**Output:** 

```py
['Geeks']
['is a', 'portal', 'for Geeks']
```