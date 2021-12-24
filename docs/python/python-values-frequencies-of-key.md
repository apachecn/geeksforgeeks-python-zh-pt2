# Python–键的频率值

> 原文:[https://www . geesforgeks . org/python-values-frequency-of-key/](https://www.geeksforgeeks.org/python-values-frequencies-of-key/)

有时，在使用 Python 字典列表时，可能会出现一个问题，即我们需要找到字典列表中特定键中所有值出现的频率。这可以应用于许多领域，包括网络开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'gfg': [1]}，{'good': [5，78，10]，' gfg': [5，6，7，8]}]
> **输出** : {8: 1，1: 1，5: 1，6: 1，7: 1}
> 
> **输入** : test_list = [{'gfg': [1，5，6，7]}]
> **输出** : {1: 1，5: 1，6: 1，7: 1}

**方法一:使用`Counter()` +列表理解**
以上功能的组合用于解决这个问题。在本文中，我们使用 Counter()执行寻找频率的任务，并使用列表理解完成计算。

```py
# Python3 code to demonstrate working of 
# Values frequencies of key
# Using Counter() + list comprehension
from collections import Counter

# initializing list
test_list = [{'gfg' : [1, 5, 6, 7], 'is' : [9, 6, 2, 10]},
             {'gfg' : [5, 6, 7, 8], 'good' : [5, 7, 10]},
             {'gfg' : [7, 5], 'best' : [5, 7]}]

# printing original list
print("The original list is : " + str(test_list))

# frequency key 
freq_key = "gfg"

# Values frequencies of key
# Using Counter() + list comprehension
res = Counter([idx for val in test_list for idx in val[freq_key]])

# printing result 
print("The frequency dictionary : " + str(dict(res))) 
```

**Output :**

> 原始列表为:[{'gfg': [1，5，6，7]，' is': [9，6，2，10]}，{'gfg': [5，6，7，8]，' good': [5，7，10]}，{'gfg': [7，5]，' best': [5，7]}]
> 
> 频率字典:{8: 1，1: 1，5: 3，6: 2，7: 3}

**方法 2:使用`chain.from_iterables() + Counter()`**
以上方法的结合可以解决这个问题。在本文中，我们使用 chain.from_iterables()执行迭代和绑定任务。

```py
# Python3 code to demonstrate working of 
# Values frequencies of key
# Using chain.from_iterables() + Counter()
from collections import Counter
import itertools

# initializing list
test_list = [{'gfg' : [1, 5, 6, 7], 'is' : [9, 6, 2, 10]},
             {'gfg' : [5, 6, 7, 8], 'good' : [5, 7, 10]},
             {'gfg' : [7, 5], 'best' : [5, 7]}]

# printing original list
print("The original list is : " + str(test_list))

# frequency key 
freq_key = "gfg"

# Values frequencies of key
# Using chain.from_iterables() + Counter()
res = Counter(itertools.chain.from_iterable([sub[freq_key] for sub in test_list]))

# printing result 
print("The frequency dictionary : " + str(dict(res))) 
```

**Output :**

> 原始列表为:[{'gfg': [1，5，6，7]，' is': [9，6，2，10]}，{'gfg': [5，6，7，8]，' good': [5，7，10]}，{'gfg': [7，5]，' best': [5，7]}]
> 
> 频率字典:{8: 1，1: 1，5: 3，6: 2，7: 3}