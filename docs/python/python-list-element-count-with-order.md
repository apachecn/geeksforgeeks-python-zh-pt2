# Python |按顺序列出元素计数

> 原文:[https://www . geesforgeks . org/python-list-element-count-with-order/](https://www.geeksforgeeks.org/python-list-element-count-with-order/)

有时，在处理列表或数字时，我们会遇到一个问题，我们需要为列表的每个元素附加一个数字，这是该元素在列表中出现的位置。这类问题可能会出现在许多领域。让我们讨论一下解决这个问题的方法。

**方法:使用`defaultdict()` +循环**
我们可以使用 defaultdict()执行这个任务，并通过仔细分配和递增元素的顺序来循环。

```py
# Python3 code to demonstrate working of
# List Element Count Order
# using defaultdict() + loop
from collections import defaultdict

# initialize list 
test_list = [1, 4, 1, 5, 4, 1, 5]

# printing original list 
print("The original list : " + str(test_list))

# List Element Count Order
# using defaultdict() + loop
temp = defaultdict(int)
res = []
for ele in test_list:
    temp[ele] += 1
    res.append((ele, temp[ele]))

# printing result
print("List elements with their order count : " + str(res))
```

**Output :**

```py
The original list : [1, 4, 1, 5, 4, 1, 5]
List elements with their order count : [(1, 1), (4, 1), (1, 2), (5, 1), (4, 2), (1, 3), (5, 2)]

```