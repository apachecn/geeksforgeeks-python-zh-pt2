# Python–按其他列表顺序重新排列列表

> 原文:[https://www . geesforgeks . org/python-按其他列表顺序重新排列列表/](https://www.geeksforgeeks.org/python-rearrange-list-by-other-list-order/)

有时，在使用 Python 列表时，我们可能会遇到需要根据其他列表顺序对列表进行排序的问题。这在许多领域都有应用，包括日常编程和学校编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这个任务可以使用列表理解来执行。在这种情况下，我们迭代排序顺序列表，如果列表出现在目标列表中，则简单地追加。根据排序顺序列表，索引是相似的。

```py
# Python3 code to demonstrate working of 
# Rearrange list by other list order
# Using list comprehension

# initializing lists
test_list1 = [5, 6, 7, 4, 8, 9, 2]
test_list2 = [9, 6, 4]

# printing original list
print("The original list 1 is : " + str(test_list1))

# printing original list
print("The original list 2 is : " + str(test_list2))

# Rearrange list by other list order
# Using list comprehension
res = [ele for ele in test_list1 if ele in test_list2]

# printing result 
print("The list after sorting is : " + str(res)) 
```

**Output :**

```py
The original list 1 is : [5, 6, 7, 4, 8, 9, 2]
The original list 2 is : [9, 6, 4]
The list after sorting is : [6, 4, 9]

```