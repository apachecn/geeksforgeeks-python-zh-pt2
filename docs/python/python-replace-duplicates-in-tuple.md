# Python |替换元组中的重复项

> 原文:[https://www . geesforgeks . org/python-replace-duplicates in tuple/](https://www.geeksforgeeks.org/python-replace-duplicates-in-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要移除出现多次的元组元素，并用一些自定义值替换双元组。让我们讨论执行这项任务的某些方法。
**方法#1:使用 set() +列表理解**
上述功能的组合可用于执行该特定任务。在这种情况下，我们只需初始化一个集合容器，然后在检查它的存在后用一个值替换重复出现的元素它在元组中的存在。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace duplicates in tuple
# using set() + list comprehension

# initialize tuple
test_tup = (1, 1, 4, 4, 4, 5, 5, 6, 7, 7)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Replace duplicates in tuple
# using set() + list comprehension
temp = set()
res = tuple(ele if ele not in temp and not temp.add(ele)
                else 'gfg' for ele in test_tup)

# printing result
print("Tuple after replacing values : " + str(res))
```

**Output : **

```py
The original tuple is : (1, 1, 4, 4, 4, 5, 5, 6, 7, 7)
Tuple after replacing values : (1, 'gfg', 4, 'gfg', 'gfg', 5, 'gfg', 6, 7, 'gfg')
```

**方法 2:使用 groupby() + loop**
上述功能的组合可以用这个问题来解决。在这种情况下，我们只是将连续的元素分组，然后用默认值替换除第一个元素之外的每个元素。仅在连续重复的情况下有效。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace duplicates in tuple
# using groupby() + loop
from itertools import groupby

# initialize tuple
test_tup = (1, 1, 4, 4, 4, 5, 5, 6, 7, 7)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Replace duplicates in tuple
# using groupby() + loop
res = tuple()
for key, ele in groupby(test_tup):
    res = res + ((key, ) + ('gfg', ) * (len(list(ele))-1))

# printing result
print("Tuple after replacing values : " + str(res))
```

**Output : **

```py
The original tuple is : (1, 1, 4, 4, 4, 5, 5, 6, 7, 7)
Tuple after replacing values : (1, 'gfg', 4, 'gfg', 'gfg', 5, 'gfg', 6, 7, 'gfg')
```