# Python–N 个大小递增列表的列表

> 原文:[https://www . geesforgeks . org/python-list-of-n-size-递增列表/](https://www.geeksforgeeks.org/python-list-of-n-size-increasing-lists/)

给定整数 N 和 M，构造递增列表直到 M，每个列表为 N 个大小，即列表的所有组合。

> **输入** : N = 2，M = 3
> **输出** : [(1，2)，(1，3)，(2，3)]
> **说明**:增加配对元素。
> 
> **输入** : N = 1，M = 4
> **输出**:【(1)、(2)、(3)、(4)】
> **解释**:增加配对元素。

**方法#1:使用循环**

这是执行这项任务的一种强力方式。在这种情况下，我们迭代元素直到 M，并形成 N 大小的列表。缺点是我们被限制在有限的列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# List of N size increasing lists
# Using loop

# initializing N
N = 2

# initializing M
M = 4

# outer loop manages lists
res = []
for idx in range(1, M):

    # inner loop manages inner elements
    for j in range(idx + 1, M + 1):
        res.append((idx, j))

# printing result 
print("The constructed combinations : " + str(res)) 
```

**Output**

```
The constructed combinations : [(1, 2), (1, 3), (1, 4), (2, 3), (2, 4), (3, 4)]

```

**方法 2:使用组合()**

这是一个内置函数，提供此解决方案所需的精确功能。解决了一行增加列表的问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# List of N size increasing lists
# Using combinations()
from itertools import combinations

# initializing N
N = 2

# initializing M
M = 4

# using combinations to perform task 
res = list(combinations(list(range(1, M + 1)), N))

# printing result 
print("The constructed combinations : " + str(res)) 
```

**Output**

```
The constructed combinations : [(1, 2), (1, 3), (1, 4), (2, 3), (2, 4), (3, 4)]

```