# Python–元组到字典求和转换

> 原文:[https://www . geesforgeks . org/python-元组到字典-求和-转换/](https://www.geeksforgeeks.org/python-tuple-to-dictionary-summation-conversion/)

有时，在使用 Python 元组时，我们会遇到这样一个问题，即元组中可能有数据点，在执行相似键的求和后，我们需要将它们转换为字典。这种操作也可以扩展到 max、min 或 product。这可能发生在数据域中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(5，8)，(5，6)，(5，2)，(5，8)，(5，10)]
> **输出** : {5: 34}
> 
> **输入** : test_list = [(5，8)，(9，6)]
> **输出** : {5: 8，9: 6}

**方法#1:使用 loop + `defaultdict()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 defaultdict()用整数初始化计数器字典，并使用循环对所有数据点进行迭代。

```
# Python3 code to demonstrate working of 
# Tuple to Dictionary Summation conversion
# Using defaultdict() + loop
from collections import defaultdict

# initializing list
test_list = [(7, 8), (5, 6), (7, 2), (6, 8), (5, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Tuple to Dictionary Summation conversion
# Using defaultdict() + loop
res = defaultdict(int)
for sub in test_list:
    res[sub[0]] += sub[1]

# printing result 
print("The summation tuple dictionary : " + str(dict(res))) 
```

**Output :**

```
The original list is : [(7, 8), (5, 6), (7, 2), (6, 8), (5, 10)]
The summation tuple dictionary : {7: 10, 5: 16, 6: 8}

```

**方法 2:使用`dictionary comprehension + sum() + groupby()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sum()执行求和任务，groupby()用于对相似的元素进行分组，以便进一步计算。

```
# Python3 code to demonstrate working of 
# Tuple to Dictionary Summation conversion
# Using dictionary comprehension + sum() + groupby()
from itertools import groupby

# initializing list
test_list = [(7, 8), (5, 6), (7, 2), (6, 8), (5, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Tuple to Dictionary Summation conversion
# Using dictionary comprehension + sum() + groupby()
fnc = lambda ele: ele[0]
res = {key: sum(sub[1] for sub in val) for key, val in groupby(
                       sorted(test_list, key = fnc), key = fnc)}

# printing result 
print("The summation tuple dictionary : " + str(res)) 
```

**Output :**

```
The original list is : [(7, 8), (5, 6), (7, 2), (6, 8), (5, 10)]
The summation tuple dictionary : {7: 10, 5: 16, 6: 8}

```