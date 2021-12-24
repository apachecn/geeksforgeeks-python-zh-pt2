# Python–保留其他列表中的 K 个匹配索引值

> 原文:[https://www . geesforgeks . org/python-retain-k-match-index-values-from-other-list/](https://www.geeksforgeeks.org/python-retain-k-match-index-values-from-other-list/)

有时，在使用 Python 列表时，我们可能会遇到这样一个问题，即我们只需要在同一索引处保留与相应列表中的特定值相匹配的字符串。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip()`**
上述功能的组合可用于执行该任务。在这种情况下，我们在选择性地压缩匹配 k 的两个列表之后提取列表。

```py
# Python3 code to demonstrate 
# Retain K match index values from other list
# using zip() + list comprehension

# Initializing lists
test_list1 = ['Gfg', 'is', 'best', 'for', 'Geeks', 'and', 'CS']
test_list2 = [4, 1, 4, 3, 4, 2, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Initializing K 
K = 4

# Group elements from Dual List Matrix
# using zip() + list comprehension
res = [x for x, y in zip(test_list1, test_list2) if y == K]

# printing result 
print ("The filtered list : " + str(res))
```

**Output :**

> 原列表 1 为:['Gfg '，' is '，' best '，' for '，' Geeks '，' CS']
> 原列表 2 为:【4，1，4，3，4，2，4】
> 过滤后的列表:['Gfg '，' best '，' Geeks '，' CS']