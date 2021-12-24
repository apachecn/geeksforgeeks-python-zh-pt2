# Python–矩阵元素频率计数器

> 原文:[https://www . geesforgeks . org/python-matrix-elements-frequency-counter/](https://www.geeksforgeeks.org/python-matrix-elements-frequencies-counter/)

有时，在使用 python Matrix 时，我们可能会遇到一个问题，即我们需要找到 Matrix 中所有元素的频率。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`Counter() + sum() + map()`**
以上方法的组合可以用来执行此任务。在本例中，我们使用 Counter()执行元素计数任务，并使用 sum()和 map()将逻辑扩展到每一行。

```py
# Python3 code to demonstrate 
# Matrix elements Frequencies Counter
# using Counter() + sum() + map()
from collections import Counter

# Initializing list
test_list = [[4, 5, 6], [2, 4, 5], [6, 7, 5]]

# printing original list
print("The original list is : " + str(test_list))

# Matrix elements Frequencies Counter
# using Counter() + sum() + map()
res = dict(sum(map(Counter, test_list), Counter()))

# printing result 
print ("The frequencies dictionary is : " + str(res))
```

**Output :**

```py
The original list is : [[4, 5, 6], [2, 4, 5], [6, 7, 5]]
The frequencies dictionary is : {2: 1, 4: 2, 5: 3, 6: 2, 7: 1}

```