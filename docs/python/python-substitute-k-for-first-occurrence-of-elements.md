# Python–用 K 代替元素的第一次出现

> 原文:[https://www . geesforgeks . org/python-replace-k-for-first-occurrence-of-elements/](https://www.geeksforgeeks.org/python-substitute-k-for-first-occurrence-of-elements/)

有时，在处理 Python 数据时，我们会遇到一个问题，我们需要对列表中每个元素的第一次出现进行替换。这种类型的问题可以应用于各种领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [4，3，3]，K = 10
> **输出** : [10，10，3]
> 
> **输入** : test_list = [4，3，7]，K = 8
> **输出** : [8，8，8]

**方法#1:使用循环**
这是解决这个问题的蛮方法。在这种情况下，我们对列表中的每个元素运行一个循环，并存储已经发生的元素进行查找，并相应地分配 k。

```
# Python3 code to demonstrate working of 
# Substitute K for first occurrence of elements
# Using loop

# initializing list
test_list = [4, 3, 3, 7, 8, 7, 4, 6, 3] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 10

# Substitute K for first occurrence of elements
# Using loop
lookp = set()
res = []
for ele in test_list:
    if ele not in lookp:
        lookp.add(ele)
        res.append(K)
    else:
        res.append(ele)

# printing result 
print("List after Substitution : " + str(res))
```

**Output :**

```
The original list is : [4, 3, 3, 7, 8, 7, 4, 6, 3]
List after Substitution : [10, 10, 3, 10, 10, 7, 4, 10, 3]

```

**方法二:使用`defaultdict() + next()` +计数+列表理解**
以上功能的组合提供了解决这个问题的速记。在本例中，我们使用 count 执行检查第一次出现的任务，next()返回 if 元素的第一次出现，并创建由第一次出现的 1 和重复的 0 组成的布尔列表。使用列表理解将这些转换为期望的结果。

```
# Python3 code to demonstrate working of 
# Substitute K for first occurrence of elements
# Using defaultdict() + next() + count + list comprehension
from itertools import count
from collections import defaultdict

# initializing list
test_list = [4, 3, 3, 7, 8, 7, 4, 6, 3] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 10

# Substitute K for first occurrence of elements
# Using defaultdict() + next() + count + list comprehension
freq = defaultdict(count)
temp = [int(next(freq[val]) == 0) for val in test_list]
res = [K if ele else test_list[idx] for idx, ele in enumerate(temp)]

# printing result 
print("List after Substitution : " + str(res))
```

**Output :**

```
The original list is : [4, 3, 3, 7, 8, 7, 4, 6, 3]
List after Substitution : [10, 10, 3, 10, 10, 7, 4, 10, 3]

```