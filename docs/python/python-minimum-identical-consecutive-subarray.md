# Python–最小相同连续子阵列

> 原文:[https://www . geesforgeks . org/python-最小-相同-连续-subarray/](https://www.geeksforgeeks.org/python-minimum-identical-consecutive-subarray/)

有时，在使用 Python 列表或在竞争性编程设置中，我们可能会遇到一个子问题，在这个子问题中，我们需要获得具有最小连续出现次数的元素。解决方案的知识可能会有很大的帮助，并且可以在任何需要的时候使用。让我们讨论一下执行这项任务的特定方式。

**使用`groupby() + min()`+λ**

这个任务可以使用上述功能的组合来解决。在这种情况下，我们使用 groupby()对每个数字的出现进行分组，并使用 min()得到它的最小值。lambda 函数提供了执行该任务实用逻辑。

```
# Python3 code to demonstrate working of
# Minimum identical consecutive Subarray
# using groupby() + min() + lambda
from itertools import groupby

# initializing list
test_list = [1, 1, 1, 2, 2, 5, 5, 5, 5]

# printing original list
print("The original list is : " + str(test_list))

# Minimum identical consecutive Subarray
# using groupby() + min() + lambda
temp = groupby(test_list)
res = min(temp, key = lambda sub: len(list(sub[1])))

# printing result 
print("Minimum Consecutive identical Occurring number is : " + str(res[0]))
```

**输出:**

```
The original list is : [1, 1, 1, 2, 2, 5, 5, 5, 5]
Minimum Consecutive identical Occurring number is : 2

```