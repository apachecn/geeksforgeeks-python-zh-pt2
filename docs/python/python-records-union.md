# Python |记录联盟

> 原文:[https://www.geeksforgeeks.org/python-records-union/](https://www.geeksforgeeks.org/python-records-union/)

有时，在处理数据时，我们可能会遇到一个问题，那就是我们需要找到我们收到的两个列表之间的所有记录。这是一个非常常见的问题，记录通常以元组的形式出现。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
可以选择列表理解作为在一行中执行该任务的方法，而不是运行循环来查找并集元素。在这种情况下，我们只是迭代单个列表，并检查是否有任何元素出现在其他列表中。如果没有，我们再次填充制作列表。

```
# Python3 code to demonstrate working of
# Records Union
# Using list comprehension

# Initializing lists
test_list1 = [('gfg', 1), ('is', 2), ('best', 3)]
test_list2 = [('i', 3), ('love', 4), ('gfg', 1)]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Records Union
# Using list comprehension
res1 = [ele1 for ele1 in test_list1]
res2 = [ele2 for ele2 in test_list2 if ele2 not in res1]
res = res1 + res2

# printing result
print("The union of data records is : " + str(res))
```

**Output :**

```
The original list 1 is : [('gfg', 1), ('is', 2), ('best', 3)]
The original list 2 is : [('i', 3), ('love', 4), ('gfg', 1)]
The union of data records is : [('gfg', 1), ('is', 2), ('best', 3), ('i', 3), ('love', 4)]

```