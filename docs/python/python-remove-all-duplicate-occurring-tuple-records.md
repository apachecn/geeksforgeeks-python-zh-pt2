# Python–删除所有重复出现的元组记录

> 原文:[https://www . geesforgeks . org/python-移除所有重复出现的元组记录/](https://www.geeksforgeeks.org/python-remove-all-duplicate-occurring-tuple-records/)

有时，在处理记录时，我们可能会遇到删除那些出现多次的记录的问题。这种应用可以出现在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `set() + count()`**
可以应用的初始方法是，我们可以迭代每个元组，并使用 count()检查它在列表中的计数，如果大于 1，我们可以移除它们，然后转换为 set。

```
# Python3 code to demonstrate working of
# Remove all Duplicate occurring records
# Using list comprehension + set() + count()

# initialize list
test_list = [(3, 4), (4, 5), (3, 4), (3, 6), (4, 5), (6, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Remove all Duplicate occurring records
# Using list comprehension + set() + count()
res = list(set([ele for ele in test_list if not test_list.count(ele) > 1]))

# printing result
print("All the non Duplicate from list are : " + str(res))
```

**Output :**

```
The original list : [(3, 4), (4, 5), (3, 4), (3, 6), (4, 5), (6, 7)]
All the non Duplicate from list are : [(6, 7), (3, 6)]

```