# Python–唯一的 Kth 定位元组

> 原文:[https://www . geesforgeks . org/python-unique-kth-posted-元组/](https://www.geeksforgeeks.org/python-unique-kth-positioned-tuples/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要根据元组的某个特定索引，只提取唯一的元组。这种问题在 web 开发等领域可能会有应用。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [(5，6，5)，(4，2，7)，(1，2，3)，(9，6，5)]
> K = 3
> **输出** : [(1，2，3)，(5，6，5)，(4，2，7)]
> **输入** :
> test_list = [(5)、(1)、(1)、(1)、(1)、(1)、(2)、(9)】
> K = 1

**方法#1:使用`map() + next()` +λ**
以上功能的组合可以解决这个问题。在本文中，我们扩展了使用 lambda 函数和 next()，使用 map()提取唯一元素的逻辑。

```py
# Python3 code to demonstrate working of 
# Unique Kth index tuples
# Using map() + next() + lambda

# initializing list
test_list = [(5, 6, 8), (4, 2, 7), (1, 2, 3), (9, 6, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Unique Kth index tuples
# Using map() + next() + lambda
res = [*map(lambda ele: next(tup for tup in test_list if tup[K - 1] == ele),
      {tup[K - 1] for tup in test_list})]

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(5, 6, 8), (4, 2, 7), (1, 2, 3), (9, 6, 5)]
The extracted elements : [(4, 2, 7), (5, 6, 8)]

```

**方法 2:使用`next() + groupby() + lambda`**
以上功能的组合也可以用来解决这个问题。在这种情况下，我们使用 groupby()以更紧凑的方式执行上面的 map()任务。

```py
# Python3 code to demonstrate working of 
# Unique Kth index tuples
# Using next() + groupby() + lambda
from itertools import groupby

# initializing list
test_list = [(5, 6, 8), (4, 2, 7), (1, 2, 3), (9, 6, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Unique Kth index tuples
# Using next() + groupby() + lambda
temp = lambda ele : ele[K - 1]
res = [next(val) for _, val in groupby(sorted(test_list, key = temp), key = temp)]

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(5, 6, 8), (4, 2, 7), (1, 2, 3), (9, 6, 5)]
The extracted elements : [(4, 2, 7), (5, 6, 8)]

```