# Python–连续正元素的最大长度

> 原文:[https://www . geesforgeks . org/python-最大长度-连续-正元素/](https://www.geeksforgeeks.org/python-maximum-length-consecutive-positive-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们监控一个序列，我们需要找到当只有正元素出现时的最大长度。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [4，5，4，1，7，2，5，6，-2，-9，-10]
> 输出 : 8
> 
> **输入** : test_list = [4，-5，-4，-1，-7，2，5，-6，-2，-9，-10]
> 输出 : 2

**方法#1:使用循环**
这是我们执行这个任务的方式之一。以这种强力的方式，我们迭代所有的元素，并不断更新 max，只要正元素链被打破。

```py
# Python3 code to demonstrate working of 
# Maximum length consecutive positive elements
# Using loop

# initializing list
test_list = [4, 5, -4, -1, -7, 2, 5, 6, -2, -9, -10]

# printing original list 
print("The original list : " + str(test_list))

# Maximum length consecutive positive elements
# Using loop
counter = 0           
max_score = 1
for ele in test_list:
    if ele > 0:
        counter += 1
    else:
        if(counter > 0):
            max_score = max(max_score, counter)
        counter = 0
if(counter > 0):
        max_score = max(max_score, counter)

# printing result 
print("Maximum elements run length : " + str(max_score))
```

**Output :**

```py
The original list : [4, 5, -4, -1, -7, 2, 5, 6, -2, -9, -10]
Maximum elements run length : 3

```

**方法 2:使用`groupby() + defaultDict() + max()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 groupby()执行分组任务，我们可以通过将负最大值和正最大值按不同的键分组来执行查找它们的最大值的任务，并使用 max()在末尾查找列表的最大值。

```py
# Python3 code to demonstrate working of 
# Maximum length consecutive positive elements
# Using groupby() + defaultDict() + max()
from collections import defaultdict
from itertools import groupby

# initializing list
test_list = [4, 5, -4, -1, -7, 2, 5, 6, -2, -9, -10]

# printing original list 
print("The original list : " + str(test_list))

# Maximum length consecutive positive elements
# Using groupby() + defaultDict() + max()
counter = defaultdict(list)
for key, val in groupby(test_list, lambda ele: "plus" if ele >= 0 else "minus"):
    counter[key].append(len(list(val)))
res = []
for key in ('plus', 'minus'):
    res.append(counter[key])

# printing result 
print("Maximum elements run length : " + str(max(res[0])))
print("Maximum negative elements run length : " + str(max(res[1])))
```

**Output :**

```py
The original list : [4, 5, -4, -1, -7, 2, 5, 6, -2, -9, -10]
Maximum elements run length : 3
Maximum negative elements run length : 3

```