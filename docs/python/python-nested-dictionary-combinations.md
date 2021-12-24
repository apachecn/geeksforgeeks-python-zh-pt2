# Python–嵌套词典组合

> 原文:[https://www . geesforgeks . org/python-嵌套-字典-组合/](https://www.geeksforgeeks.org/python-nested-dictionary-combinations/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要构造具有不同值的字典键的所有组合。这个问题可以应用于游戏和日常编程等领域。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_dict = {'gfg': {'is' : [6]，' for' : [10]，' best': [4]}}
> **输出** : {'gfg0': {'for': 10，' best': 4，' is': 6}}
> 
> **输入**:test _ dict = { ' gfg ':{ ' best ':[10]} }
> **输出** : {'gfg0': {'best': 10}}

**方法:使用`product() + dictionary comprehension + zip()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 product 提取所有可能的组合，zip()执行将键与过滤后的值配对的任务，字典理解用于存储所有构建的字典。

```py
# Python3 code to demonstrate working of 
# Nested dictionary Combinations
# Using product() + dictionary comprehension + zip()
from itertools import product

# initializing dictionary
test_dict = {'gfg': {'is' : [6, 7, 8], 'best': [1, 9, 4]}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Nested dictionary Combinations
# Using product() + dictionary comprehension + zip()
res = { key + str(j) : dict(zip(val.keys(), k))
        for key, val in test_dict.items()
        for j, k in enumerate(product(*val.values()))}

# printing result 
print("The possible combinations : " + str(res)) 
```

**Output :**

> 原始字典:{'gfg': {'is': [6，7，8]，' best': [1，9，4]}}
> 可能的组合:{'gfg5': {'is': 7，' best': 4}，' gfg3': {'is': 7，' best': 1}，' gfg8': {'is': 8，' best': 4}，' gfg2': {'is': 6，' best': 4}，' gfg6': {'is': 8，' best': 1}，' 0 '