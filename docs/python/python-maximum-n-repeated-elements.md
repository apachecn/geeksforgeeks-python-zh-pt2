# Python–最大 N 个重复元素

> 原文:[https://www . geesforgeks . org/python-maximum-n-repeated-elements/](https://www.geeksforgeeks.org/python-maximum-n-repeated-elements/)

给定元素列表，如果一个元素在列表中的出现次数增加超过 n，则将其移除

> **输入** : test_list = [6，4，6，3，6]，N = 1
> 
> **输出**:【6，4，3】
> 
> **说明**:6 的第 2 个开始被删除。
> 
> **输入** : test_list = [6，4，6，3，6]，N = 2
> 
> **输出**:【6，4，6，3】
> 
> **说明**:删除第 3 次及以后的 6 次。

**方法#1:使用循环+计数()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们执行元素的迭代，并使用 count()检查该元素的计数是否大于 N，如果是，则移除该元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum N repeated Elements
# Using loop + count()

# initializing list
test_list = [5, 7, 7, 2, 5, 5, 7, 2, 2]

# printing original list
print("The original list : " + str(test_list))

# initializing N
N = 2

# Using loop + count()
res = []
for ele in test_list:

    # checking of elements occurrence is not greater than N
    if res.count(ele) < N:
        res.append(ele)

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```py
The original list : [5, 7, 7, 2, 5, 5, 7, 2, 2]
Extracted elements : [5, 7, 7, 2, 5, 2]

```

**方法 2:使用 Counter() +循环**

这是执行这项任务的另一种方式。在这种情况下，我们使用 Counter()对元素进行计数，如果小于 N，则追加其大小的元素，如果大于 N，则使用列表理解来扩展元素，直到 N。不保持顺序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum N repeated Elements
# Using Counter() + loop
from collections import Counter

# initializing list
test_list = [5, 7, 7, 2, 5, 5, 7, 2, 2]

# printing original list
print("The original list : " + str(test_list))

# initializing N
N = 2

# Using Counter() + loop
res = []
temp = Counter(test_list)
for key, ele in temp.items():

    # Conditional check for size decision during append
    if ele <= N:
        res.extend([key for idx in range(ele)])
    else:
        res.extend([key for idx in range(N)])

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```py
The original list : [5, 7, 7, 2, 5, 5, 7, 2, 2]
Extracted elements : [5, 5, 7, 7, 2, 2]

```