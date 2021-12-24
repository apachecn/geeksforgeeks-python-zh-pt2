# Python–连续元素的重新排序

> 原文:[https://www . geeksforgeeks . org/python-为连续元素重新排序/](https://www.geeksforgeeks.org/python-reorder-for-consecutive-elements/)

给定一个列表，执行重新排序以获得连续的相似元素。

> **输入** : test_list = [4，7，5，4，1，4，1，6，7，5]
> **输出** : [4，4，4，7，7，5，5，1，1，6]
> **解释**:所有相似的元素都被赋值为连续的。
> 
> **输入** : test_list = [4，7，5，1，4，1，6，7，5]
> **输出** : [4，4，7，7，5，5，1，1，6]
> **解释**:所有相似的元素都被赋值为连续的。

**方法#1:使用 Counter() + loop + items()**

在本文中，我们使用 Counter()执行计算频率的任务，并使用 loop 和 items()分别根据计数和访问频率对元素进行重新排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Reorder for consecutive elements
# Using Counter() + loop + items()
from collections import Counter

# initializing list
test_list = [4, 7, 5, 4, 1, 4, 1, 6, 7, 5]

# printing original lists
print("The original list is : " + str(test_list))

# getting frequency
freqs = Counter(test_list)
res = []

# reordering basis of frequency
for val, cnt in freqs.items():
    res.extend([val]*cnt)

# printing result 
print("Reordered List : " + str(res))
```

**输出:**

```py
The original list is : [4, 7, 5, 4, 1, 4, 1, 6, 7, 5]
Reordered List : [4, 4, 4, 7, 7, 5, 5, 1, 1, 6]

```

**方法 2:使用 Counter() + elements()**

在本文中，我们使用元素()执行重新排序计数频率的任务，提供了一个简洁的解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Reorder for consecutive elements
# Using Counter() + elements()
from collections import Counter

# initializing list
test_list = [4, 7, 5, 4, 1, 4, 1, 6, 7, 5]

# printing original lists
print("The original list is : " + str(test_list))

# reordering using elements()
res = list(Counter(test_list).elements())

# printing result 
print("Reordered List : " + str(res))
```

**输出:**

```py
The original list is : [4, 7, 5, 4, 1, 4, 1, 6, 7, 5]
Reordered List : [4, 4, 4, 7, 7, 5, 5, 1, 1, 6]

```