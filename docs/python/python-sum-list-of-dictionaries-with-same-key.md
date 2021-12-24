# Python |同键字典汇总列表

> 原文:[https://www . geesforgeks . org/python-sum-同键字典列表/](https://www.geeksforgeeks.org/python-sum-list-of-dictionaries-with-same-key/)

您已经给出了一个字典列表，任务是用相同的键返回一个带有和值的字典。

让我们讨论做这项任务的不同方法。

**方法#1:使用`reduce() + operator`**

```py
# Python code to demonstrate
# return the sum of values of dictionary
# with same keys in list of dictionary

import collections, functools, operator

# Initialising list of dictionary
ini_dict = [{'a':5, 'b':10, 'c':90},
            {'a':45, 'b':78}, 
            {'a':90, 'c':10}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# sum the values with same keys
result = dict(functools.reduce(operator.add,
         map(collections.Counter, ini_dict)))

print("resultant dictionary : ", str(result))
```

**Output:**

> 初始词典[{'b': 10，' a': 5，' c': 90}，{'b': 78，' a': 45}，{'a': 90，' c': 10}]
> 结果词典:{'b': 88，' a': 140，' c': 100}

**方法 2:使用计数器**

```py
# Python code to demonstrate
# return the sum of values of dictionary
# with same keys in list of dictionary

import collections

# Initialising list of dictionary
ini_dict = [{'a':5, 'b':10, 'c':90}, 
            {'a':45, 'b':78},
            {'a':90, 'c':10}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# sum the values with same keys
counter = collections.Counter()
for d in ini_dict: 
    counter.update(d)

result = dict(counter)

print("resultant dictionary : ", str(counter))
```

**Output:**

> 初始字典[{'c': 90，' a': 5，' b': 10}，{'a': 45，' b': 78}，{'a': 90，' c': 10}]
> 结果字典:Counter({'a': 140，' c': 100，' b': 88})

**方法#3:天真法**

```py
# Python code to demonstrate
# return the sum of values of dictionary
# with same keys in list of dictionary

from operator import itemgetter

# Initialising list of dictionary
ini_dict = [{'a':5, 'b':10, 'c':90},
            {'a':45, 'b':78}, 
            {'a':90, 'c':10}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# sum the values with same keys
result = {}
for d in ini_dict:
    for k in d.keys():
        result[k] = result.get(k, 0) + d[k]

print("resultant dictionary : ", str(result))
```

**Output:**

> 初始词典[{'b': 10，' c': 90，' a': 5}，{'b': 78，' a': 45}，{'c': 10，' a': 90}]
> 结果词典:{'b': 88，' c': 100，' a': 140}