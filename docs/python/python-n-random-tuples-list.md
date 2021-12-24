# Python–N 随机元组列表

> 原文:[https://www.geeksforgeeks.org/python-n-random-tuples-list/](https://www.geeksforgeeks.org/python-n-random-tuples-list/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要构建随机元组列表。这可以应用于许多领域使用游戏和日常编程。让我们讨论执行这项任务的某些方法。

> **输入**:
> N = 4
> R = 6
> T5】输出 : [(5，6)，(1，0)，(1，3)，(2，3)]
> **输入** :
> N = 8
> R = 4
> **输出** : [(2，3)，(4，1)，(2，0)，(4，3)，(4，2)，(0)，(0，2)，(1，4)，(0，1)，(0，1，1)]

**方法#1:使用列表理解+ `sample()`**
这是可以执行此任务的方式之一。在这种情况下，随机数生成使用 sample()进行，当给定的数字池提取随机数以形成对时，这些对使用列表理解进行配对。

```py
# Python3 code to demonstrate working of 
# N Random Tuples list
# Using list comprehension + sample()
import random

# initializing N
N = 5

# initializing Tuple element range 
R = 10

# N Random Tuples list
# Using list comprehension + sample()
res = [divmod(ele, R + 1) for ele in random.sample(range((R + 1) * (R + 1)), N)]

# printing result 
print("The N random tuples : " + str(res)) 
```

**Output :**

```py
The N random tuples : [(2, 5), (6, 10), (4, 7), (10, 2), (2, 2)]

```

**方法 2:使用`product() + sample()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用乘积()执行在一个范围内产生数字的任务，样本()用于从中提取 N 个随机数。

```py
# Python3 code to demonstrate working of 
# N Random Tuples list
# Using product() + sample()
import random
import itertools

# initializing N
N = 5

# initializing Tuple element range 
R = 10

# N Random Tuples list
# Using product() + sample()
res = random.sample(list(itertools.product(range(R + 1), repeat = 2)), N)

# printing result 
print("The N random tuples : " + str(res)) 
```

**Output :**

```py
The N random tuples : [(2, 5), (6, 10), (4, 7), (10, 2), (2, 2)]

```