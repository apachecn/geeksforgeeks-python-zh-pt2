# Python |记录相似元组出现次数

> 原文:[https://www . geesforgeks . org/python-记录-相似-元组-出现次数/](https://www.geeksforgeeks.org/python-record-similar-tuple-occurrences/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要检查发生在相似时间的记录的出现情况。这在网络开发领域有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`map() + Counter()` +排序后的**

上述功能的组合可用于执行该任务。在这种情况下，我们在向`Counter()`馈送数据之前，为了计数出现，对数据进行排序，使所有无序元组有序，以将相似元组计数为一。

```py
# Python3 code to demonstrate working of
# Record Similar tuple occurrences
# Using Counter() + map() + sorted
from collections import Counter

# initialize list 
test_list = [(3, 1), (1, 3), (2, 5), (5, 2), (6, 3)]

# printing original list
print("The original list is : " + str(test_list))

# Record Similar tuple occurrences
# Using Counter() + map() + sorted
res = dict(Counter(tuple(ele) for ele in map(sorted, test_list)))

# printing result
print("The frequency of like tuples : " + str(res))
```

**Output :**

```py
The original list is : [(3, 1), (1, 3), (2, 5), (5, 2), (6, 3)]
The frequency of like tuples : {(2, 5): 2, (1, 3): 2, (3, 6): 1}

```

**方法 2:使用`frozenset() + Counter()`**

上述功能的组合可用于执行该特定任务。在这种情况下，`sorted and map()` 执行的任务由内部排序元组的`frozenset()`执行。

```py
# Python3 code to demonstrate working of
# Record Similar tuple occurrences
# Using frozenset() + Counter()
from collections import Counter

# initialize list 
test_list = [(3, 1), (1, 3), (2, 5), (5, 2), (6, 3)]

# printing original list
print("The original list is : " + str(test_list))

# Record Similar tuple occurrences
# Using frozenset() + Counter()
res = dict(Counter(tuple(frozenset(ele)) for ele in test_list))

# printing result
print("The frequency of like tuples : " + str(res))
```

**Output :**

```py
The original list is : [(3, 1), (1, 3), (2, 5), (5, 2), (6, 3)]
The frequency of like tuples : {(2, 5): 2, (1, 3): 2, (3, 6): 1}

```