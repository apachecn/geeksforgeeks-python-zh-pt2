# Python–矩阵中最常见的组合

> 原文:[https://www . geesforgeks . org/python-最常见的矩阵组合/](https://www.geeksforgeeks.org/python-most-common-combination-in-matrix/)

给定一个矩阵，任务是编写一个 python 程序来提取任何大于 2 的元素组合的最常见出现。

**示例:**

> **输入:** test_list = [[4，5，6，2]，[7，6，3，2]，[4，2，6，7]，[1，2，4，6]]
> 
> **输出:** [(2，6)]
> 
> **说明:**【2，6】组合出现 4 次，最多。
> 
> **输入:** test_list = [[4，5，6，2]，[7，6，3，2]，[4，2，6，7]，[1，2，4，7]]
> 
> **输出:** [(2，4)，(2，6)，(2，7)]
> 
> **说明:**【2，6】、【2，4】和【2，7】组合出现各 3 次，最多。

**方法:**使用[组合()](https://www.geeksforgeeks.org/itertools-combinations-module-python-print-possible-combinations/) + [计数器()](https://www.geeksforgeeks.org/counters-in-python-set-1/) + [最常见的()](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/) + [列表理解](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，使用*组合()*、*计数器()*计算组合，跟踪每个组合的频率。最后，利用*最常见()*提取组合出现的最大频率。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Most common Combination in Matrix

# import required modules
from collections import Counter
from itertools import combinations

# initializing list
test_list = [[4, 5, 6, 2], [7, 6, 3, 2],
             [4, 2, 6, 7], [1, 2, 4, 6]]

# printing original list
print("The original list is : " + str(test_list))

res = Counter()
for sub in test_list:

    # ignoring 1 sized substring
    if len(sub) < 2:
        continue

    # sorting for common ordering
    sub.sort()

    # getting and storing combinations
    for size in range(2, len(sub) + 1):
        for comb in combinations(sub, size):
            res[comb] += 1

# getting most common combinations
res = [cmb for cmb, 
       cnt in res.items() if cnt == res.most_common(1)[0][1]]

# printing result
print("The Most common combination : " + str(res))
```

**输出:**

```
The original list is : [[4, 5, 6, 2], [7, 6, 3, 2], [4, 2, 6, 7], [1, 2, 4, 6]]
The Most common combination : [(2, 6)]
```