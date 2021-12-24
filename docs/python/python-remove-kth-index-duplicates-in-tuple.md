# Python–删除元组中的第 k 个索引重复项

> 原文:[https://www . geesforgeks . org/python-remove-kth-index-duplicates-in-tuple/](https://www.geeksforgeeks.org/python-remove-kth-index-duplicates-in-tuple/)

有时，在使用 Python 记录时，我们可能会遇到一个问题，即我们需要移除所有元组，这些元组在记录列表中具有相似的 Kth 索引元素。这种问题在日常和 web 开发领域都很常见。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，5，6)，(2，3，4)，(1，3，4)，(7，6，4)，(1，2，6)]，K = 1
> **输出** : [(4，5，6)，(2，3，4)，(7，6，4)，(1，2，6)]
> 
> **输入** : test_list = [(4，5，6)，(2，3，4)，(1，3，4)，(7，6，4)，(1，2，6)]，K = 0
> **输出** : [(4，5，6)，(2，3，4)，(1，3，4)，(7，6，4)]

**方法#1:使用循环**
这是执行该任务的方法之一。在这种情况下，我们执行记忆集合中已经出现的第 Kth 个索引元素的任务，并使用新的值检查每次。

```
# Python3 code to demonstrate working of 
# Remove Kth Index Duplicates in Tuple
# Using loop

# initializing lists
test_list = [(4, 5, 6), (2, 3, 4), (1, 3, 4), (7, 6, 4), (1, 2, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# Remove Kth Index Duplicates in Tuple
# Using loop
keep = set()      
res = []
for sub in test_list:
    if sub[K] not in keep:
        res.append(sub)
        keep.add(sub[K])

# printing result 
print("Filtered Tuples : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5, 6), (2, 3, 4), (1, 3, 4), (7, 6, 4), (1, 2, 6)]
Filtered Tuples : [(4, 5, 6), (2, 3, 4)]

```

**方法二:使用`groupby() + itemgetter()` +列表理解**
以上功能的组合可以解决这个问题。在本例中，我们使用 itemgetter()执行检查 Kth 元素的任务，groupby()用于形成组，我们通过访问第 0 个索引从组中提取第 1 个元素。

```
# Python3 code to demonstrate working of 
# Remove Kth Index Duplicates in Tuple
# Using groupby() + itemgetter() + list comprehension
from itertools import groupby
from operator import itemgetter

# initializing lists
test_list = [(4, 5, 6), (2, 3, 4), (1, 3, 4), (7, 6, 4), (1, 2, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# Remove Kth Index Duplicates in Tuple
# Using groupby() + itemgetter() + list comprehension
res = res = [list(val)[0] for key, val in groupby(sorted(test_list, 
                        key = itemgetter(K)), key = itemgetter(K))]

# printing result 
print("Filtered Tuples : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5, 6), (2, 3, 4), (1, 3, 4), (7, 6, 4), (1, 2, 6)]
Filtered Tuples : [(4, 5, 6), (2, 3, 4)]

```