# Python |元素之间的最大距离

> 原文:[https://www . geesforgeks . org/python-元素间最大距离/](https://www.geeksforgeeks.org/python-maximum-distance-between-elements/)

有时，在处理列表时，我们可能会遇到一个问题，即我们需要找到重复元素之间的最大距离。这类问题可以应用于竞争性编程和 web 开发领域。让我们讨论一下执行这项任务的具体方法。

**方法:使用 loop + `max() + defaultdict() + enumerate()`**
以上功能的组合可以用来执行这个特定的任务。在本文中，我们首先使用 defaultdict()用 list 初始化 temp dict。迭代使用枚举()和 max()来计算列表中所有相似数字之间的最大距离。

```py
# Python3 code to demonstrate 
# Maximum distance between elements
# using max() + enumerate() + loop + defaultdict()
from collections import defaultdict

# Initializing list
test_list = [4, 5, 6, 4, 6, 3]

# printing original list
print("The original list is : " + str(test_list))

# Maximum distance between elements
# using max() + enumerate() + loop + defaultdict()
temp = defaultdict(list)
for idx, ele in enumerate(test_list):
    temp[ele].append(idx)
res = max(temp[ele][-1]-temp[ele][0] for ele in temp)

# printing result 
print ("Maximum distance between same element is : " + str(res))
```

**Output :**

```py
The original list is : [4, 5, 6, 4, 6, 3]
Maximum distance between same element is : 3

```