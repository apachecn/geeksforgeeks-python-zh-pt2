# Python–字典键的最小值配对

> 原文:[https://www . geeksforgeeks . org/python-字典键最小值配对/](https://www.geeksforgeeks.org/python-minimum-value-pairing-for-dictionary-keys/)

给定两个列表，键和值，构造一个字典，在相似的键值配对的情况下选择最小值。

> **输入** : test_list1 = [4，7，4，8]，test_list2 = [5，7，2，9]
> **输出** : {8: 9，7: 7，4: 2}
> **说明**:4 有 2 个选项，5 和 2，2 最小为成对。
> 
> **输入** : test_list1 = [4，4，4，4]，test_list2 = [3，7，2，1]
> **输出** : {4: 1}
> **解释**:所有元素为 4，最小为 1。

**方法# 1:dict()+sorted()+zip()+lambda**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序，zip()用于将键与值进行映射。dict()用于将结果转换回字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Minimum value pairing for dictionary keys
# Using dict() + sorted() + zip() + lambda

# initializing lists
test_list1 = [4, 7, 4, 8, 7, 9]
test_list2 = [5, 7, 2, 9, 3, 4]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using zip() to bing key and value lists
# reverse sorting the list before assigning values 
# so as minimum values get to end, and hence avoided from 
# pairing 
res = dict(sorted(zip(test_list1, test_list2), key = lambda ele: -ele[1]))

# printing result 
print("The minimum paired dictionary : " + str(res))
```

**Output**

```
The original list 1 : [4, 7, 4, 8, 7, 9]
The original list 2 : [5, 7, 2, 9, 3, 4]
The minimum paired dictionary : {8: 9, 7: 3, 4: 2, 9: 4}

```

**方法 2:使用 group by()+item getter()+zip()**

上述功能的组合提供了解决这个问题的另一种方法。在这种情况下，值分组是使用 groupby()完成的，最小元素是使用 itemgetter()提取的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Minimum value pairing for dictionary keys
# Using groupby() + itemgetter() + zip()
from operator import itemgetter
from itertools import groupby

# initializing lists
test_list1 = [4, 7, 4, 8, 7, 9]
test_list2 = [5, 7, 2, 9, 3, 4]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using zip() to bind key and value lists
# groupby() to group similar value.
# 0th, first element is extracted to be smallest 
# using itemgetter()
temp = sorted(zip(test_list1, test_list2))
res = {key: min(val for _, val in group)
      for key, group in groupby(sorted(temp), itemgetter(0))}

# printing result 
print("The minimum paired dictionary : " + str(res))
```

**Output**

```
The original list 1 : [4, 7, 4, 8, 7, 9]
The original list 2 : [5, 7, 2, 9, 3, 4]
The minimum paired dictionary : {4: 2, 7: 3, 8: 9, 9: 4}

```