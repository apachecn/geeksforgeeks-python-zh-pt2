# Python–按元组列表中第二个元素的频率排序

> 原文:[https://www . geesforgeks . org/python-按元组列表中第二元素的频率排序/](https://www.geeksforgeeks.org/python-sort-by-frequency-of-second-element-in-tuple-list/)

给定元组列表，按元组第二个元素的频率排序。

> **输入** : test_list = [(6，5)，(1，7)，(2，5)，(8，7)，(9，8)，(3，7)]
> **输出** : [(1，7)，(8，7)，(3，7)，(6，5)，(2，5)，(9，8)]
> **解释** : 7 作为第二个元素出现 3 次，因此所有 7 的元组都是先对齐的。
> 
> **输入** : test_list = [(1，7)，(8，7)，(9，8)，(3，7)]
> **输出** : [(1，7)，(8，7)，(3，7)，(9，8)]
> **解释** : 7 作为第二个元素出现 3 次，因此所有 7 的元组都是先对齐的。

**方法#1:使用 sorted()+loop+default dict()+lambda**

在本文中，我们使用 defaultdict()计算频率，并使用此结果作为参数传递给 lambda 函数，以便在此基础上使用 sorted()执行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort by Frequency of second element in Tuple List
# Using sorted() + loop + defaultdict() + lambda
from collections import defaultdict

# initializing list
test_list = [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

# constructing mapping
freq_map = defaultdict(int)
for idx, val in test_list:
    freq_map[val] += 1

# performing sort of result 
res = sorted(test_list, key = lambda ele: freq_map[ele[1]], reverse = True)

# printing results
print("Sorted List of tuples : " + str(res))
```

**Output**

```py
The original list is : [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]
Sorted List of tuples : [(2, 7), (8, 7), (3, 7), (6, 5), (2, 5), (9, 8)]

```

**方法 2:使用 Counter() + lambda + sorted()**

在这种情况下，频率计算的任务是使用 Counter()完成的，其余所有功能与上述方法相似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort by Frequency of second element in Tuple List
# Using Counter() + lambda + sorted()
from collections import Counter

# initializing list
test_list = [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

# constructing mapping using Counter
freq_map = Counter(val for key, val in test_list)

# performing sort of result 
res = sorted(test_list, key = lambda ele: freq_map[ele[1]], reverse = True)

# printing results
print("Sorted List of tuples : " + str(res))
```

**Output**

```py
The original list is : [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]
Sorted List of tuples : [(2, 7), (8, 7), (3, 7), (6, 5), (2, 5), (9, 8)]

```