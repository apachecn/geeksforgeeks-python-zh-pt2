# Python–在嵌套字典中交换层次结构

> 原文:[https://www . geesforgeks . org/python-交换-嵌套层次结构-字典/](https://www.geeksforgeeks.org/python-swapping-hierarchy-in-nested-dictionaries/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要执行嵌套字典的层次交换。这个问题可以应用于需要字典重组的领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'Gfg': { 'a' : [1，3，7，8]，' b' : [4，9]，' c' : [0，7]}}
> **输出** : {'c': {'Gfg': [0，7]}，' b': {'Gfg': [4，9]}，' a': {'Gfg': [1，3，7，8]}}
> **输入** : test

**方法#1:使用 loop + items()**
以上功能的组合可以用来解决这个问题。在这种情况下，我们迭代字典并使用暴力重组。items()用于提取字典的所有键值对。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Swapping Hierarchy in Nested Dictionaries
# Using loop + items()

# initializing dictionary
test_dict = {'Gfg': { 'a' : [1, 3], 'b' : [3, 6], 'c' : [6, 7, 8]},
             'Best': { 'a' : [7, 9], 'b' : [5, 3, 2], 'd' : [0, 1, 0]}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Swapping Hierarchy in Nested Dictionaries
# Using loop + items()
res = dict()
for key, val in test_dict.items():
    for key_in, val_in in val.items():
        if key_in not in res:
            temp = dict()
        else:
            temp = res[key_in]
        temp[key] = val_in
        res[key_in] = temp

# printing result
print("The rearranged dictionary : " + str(res))
```

**Output : **

原始字典:{'Gfg': {'a': [1，3]，' c': [6，7，8]，' b': [3，6]}，' Best': {'d': [0，1，0]，' a': [7，9]，' b': [5，3，2]}}
重新排列的字典:{'d': {'Best': [0，1，0]}，' a': {'Gfg': [1，3]，' Best': [7，9]]

**方法 2:使用 defaultdict() + loop**
这是解决这个问题的又一种蛮力方式。在这种情况下，我们通过使用 defaultdict()而不是传统的字典来减少一个关键的测试步骤。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Swapping Hierarchy in Nested Dictionaries
# Using  defaultdict() + loop
from collections import defaultdict

# initializing dictionary
test_dict = {'Gfg': { 'a' : [1, 3], 'b' : [3, 6], 'c' : [6, 7, 8]},
             'Best': { 'a' : [7, 9], 'b' : [5, 3, 2], 'd' : [0, 1, 0]}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Swapping Hierarchy in Nested Dictionaries
# Using  defaultdict() + loop
res = defaultdict(dict)
for key, val in test_dict.items():
    for key_in, val_in in val.items():
        res[key_in][key] = val_in

# printing result
print("The rearranged dictionary : " + str(dict(res)))
```

**Output : **

原始字典:{'Gfg': {'a': [1，3]，' c': [6，7，8]，' b': [3，6]}，' Best': {'d': [0，1，0]，' a': [7，9]，' b': [5，3，2]}}
重新排列的字典:{'d': {'Best': [0，1，0]}，' a': {'Gfg': [1，3]，' Best': [7，9]]