# 在集合列表中查找重复集合的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-程序-在集合列表中查找重复集合/](https://www.geeksforgeeks.org/python-program-to-find-duplicate-sets-in-list-of-sets/)

给定一个集合列表，任务是编写一个 Python 程序来查找重复的集合。

> **输入:** test_list = [{4，5，6，1}，{6，4，1，5}，{1，3，4，3}，{1，4，3}，{7，8，9}]
> 
> **输出:**【frozenset({1，4，5，6})，frozenset({ 1，3，4})】
> 
> **解释:** {1，4，5，6}类似于{6，4，1，5}因此部分结果。
> 
> **输入:** test_list = [{4，5，6，9}，{6，4，1，5}，{1，3，4，3}，{1，4，3}，{7，8，9}]
> 
> **输出:**【frozenset({ 1，3，4})】
> 
> **解释:** {1，3，4} ({1，3，4，3})类似于{1，4，3}，因此部分结果。

**方法#1:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/) **+计数()+**[**frozenset()**](https://www.geeksforgeeks.org/frozenset-in-python/)**+循环**

在这种情况下，通过使用 Counter()将所有集合转换为 frozenset() [以获得 hashable type ]到 frequency，从而对它们进行哈希处理。然后 count()用于从创建的频率计数器中获取所有当前集合的计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Duplicate sets in list of sets
# Using Counter() + count() + frozenset() + loop
from collections import Counter

# initializing list
test_list = [{4, 5, 6, 1}, {6, 4, 1, 5}, {1, 3, 4, 3}, 
             {1, 4, 3}, {7, 8, 9}]

# printing original list
print("The original list is : " + str(test_list))

# getting frequency using Counter()
freqs = Counter(frozenset(sub) for sub in test_list)

res = []
for key, val in freqs.items():

    # if frequency greater than 1, set is appended 
    # [duplicate]
    if val > 1 :
        res.append(key)

# printing result
print("Duplicate sets list : " + str(res))
```

**输出:**

> 原始列表为:[{1，4，5，6}，{1，4，5，6}，{1，3，4}，{1，3，4}，{8，9，7}]
> 
> 重复集列表:[frozenset({1，4，5，6})，frozenset({1，3，4})]

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+ Counter()**

在这种情况下，我们执行类似的任务，唯一的区别是列表理解作为一个线性提取基于频率字典的重复。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Duplicate sets in list of sets
# Using list comprehension + Counter()
from collections import Counter

# initializing list
test_list = [{4, 5, 6, 1}, {6, 4, 1, 5}, {1, 3, 4, 3}, {1, 4, 3}, {7, 8, 9}]

# printing original list
print("The original list is : " + str(test_list))

# getting frequency using Counter()
freqs = Counter(frozenset(sub) for sub in test_list)

# list comprehension provides shorthand solution
res = [key for key, val in freqs.items() if val > 1]

# printing result
print("Duplicate sets list : " + str(res))
```

**输出:**

> 原始列表为:[{1，4，5，6}，{1，4，5，6}，{1，3，4}，{1，3，4}，{8，9，7}]
> 
> 重复集列表:[frozenset({1，4，5，6})，frozenset({1，3，4})]