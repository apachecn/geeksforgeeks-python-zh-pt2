# Python |合并键值列表

> 原文:[https://www.geeksforgeeks.org/python-merge-key-value-lists/](https://www.geeksforgeeks.org/python-merge-key-value-lists/)

有时，在处理列表时，我们会遇到一个问题，即我们需要执行合并功能，在该功能中，我们拥有键列表，并且需要创建字典映射键，该键在其他列表中具有相应的值。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +循环+ `defaultdict()`**
以上方法的组合可以用来执行这个特定的任务。在这种情况下，我们使用 zip 函数将列表中的相似元素相互匹配，然后使用 loop 为键赋值，从 zip 列表中为 defaultdict 赋值。

```py
# Python3 code to demonstrate working of
# Merge key value list
# Using zip() + loop + defaultdict()
from collections import defaultdict

# initializing lists
test_list1 = [0, 0, 0, 1, 1, 1, 2, 2]
test_list2 = ['gfg', 'is', 'best', 'Akash', 'Akshat', 'Nikhil', 'apple', 'grapes']

# printing original lists
print("The original list1 is : " + str(test_list1))
print("The original list2 is : " + str(test_list2))

# Using zip() + loop + defaultdict()
# Merge key value list
res = defaultdict(list)
for i, j in zip(test_list1, test_list2):
   res[i].append(j)

# printing result 
print("The merged key value dictionary is : " + str(dict(res)))
```

**Output :**

> 原列表 1 为:[0，0，0，1，1，1，2，2]
> 原列表 2 为:['gfg '，' is '，' best '，' Akash '，' Akshat '，' Nikhil '，' apple '，' grapes']
> 合并后的键值字典为:{0: ['gfg '，' is '，' best']，1: ['Akash '，' Akshat '，' Nikhil']，2: ['apple '，' grapes']