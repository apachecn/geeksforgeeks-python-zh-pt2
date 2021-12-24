# Python–唯一元组频率(顺序无关)

> 原文:[https://www . geesforgeks . org/python-unique-tuple-frequency-order-无关/](https://www.geeksforgeeks.org/python-unique-tuple-frequency-order-irrespective/)

给定元组列表，提取列表顺序中唯一元组的频率，而不考虑。

> **输入** : test_list = [(3，4)，(1，2)，(4，3)，(3，4)]
> **输出** : 2
> **解释** : (3，4)，(4，3)，(3，4)使 1 和(1，2)为第 2 唯一元素。
> 
> **输入** : test_list = [(3，7)，(1，2)，(4，3)，(5，6)]
> **输出** : 4
> **解释**:任何顺序都不一样。

**方法#1:使用`tuple() + generator expression + sorted() + len()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序任务，以消除顺序限制。len()用于计算大小。

```py
# Python3 code to demonstrate working of 
# Unique Tuple Frequency [ Order Irrespective ]
# Using tuple() + list comprehension + sorted() + len()

# initializing lists
test_list = [(3, 4), (1, 2), (4, 3), (5, 6)]

# printing original list
print("The original list is : " + str(test_list))

# Using tuple() + list comprehension + sorted() + len()
# Size computed after conversion to set
res = len(list(set(tuple(sorted(sub)) for sub in test_list)))

# printing result 
print("Unique tuples Frequency : " + str(res)) 
```

**Output :**

```py
The original list is : [(3, 4), (1, 2), (4, 3), (5, 6)]
Unique tuples Frequency : 3

```

**方法 2:使用`map() + sorted() + tuple() + set() + len()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行扩展排序逻辑和元组转换的任务，set()用于消除重复，len()用于查找容器的长度。

```py
# Python3 code to demonstrate working of 
# Unique Tuple Frequency [ Order Irrespective ]
# Using map() + sorted() + tuple() + set() + len()

# initializing lists
test_list = [(3, 4), (1, 2), (4, 3), (5, 6)]

# printing original list
print("The original list is : " + str(test_list))

# Using map() + sorted() + tuple() + set() + len()
# inner map used to perform sort and outer sort to
# convert again in tuple format
res = len(list(set(map(tuple, map(sorted, test_list)))))

# printing result 
print("Unique tuples Frequency : " + str(res)) 
```

**Output :**

```py
The original list is : [(3, 4), (1, 2), (4, 3), (5, 6)]
Unique tuples Frequency : 3

```