# Python–重新排列连续值键的字典

> 原文:[https://www . geesforgeks . org/python-重排-字典-for-conservative-value-key/](https://www.geeksforgeeks.org/python-rearrange-dictionary-for-consective-value-keys/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要重新排列字典键，以便在字典中一个值后面跟着同一个键。这个问题可以在竞争规划算法和图问题中得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {1 : 2，3 : 2，2 : 3}
> 输出 : {1: 2，2 : 3，3: 2}
> 输入 : test_dict = {1 : 2}
> **输出** : {1 : 2}

**方法#1:使用循环+按键()**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 key()提取字典键，并进行迭代，直到找到相等键后面的值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rearrange dictionary for consecutive value-keys
# Using loop + keys()

# initializing dictionary
test_dict = {1 : 3, 4 : 5, 3 : 4, 5 : 6}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Rearrange dictionary for consecutive value-keys
# Using loop + keys()
temp = list(test_dict.keys())[0]
res = {}
while len(test_dict) > len(res):
    res[temp] = temp = test_dict[temp]

# printing result
print("The rearranged dictionary : " + str(res))
```

**Output : **

```py
The original dictionary : {1: 3, 4: 5, 3: 4, 5: 6}
The rearranged dictionary : {1: 3, 3: 4, 4: 5, 5: 6}
```

**方法 2:利用字典理解+累加()**
以上功能的组合可以用来解决这个问题。在本文中，我们使用积累来完成配对任务，并使用词典理解来重新排列新词典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Rearrange dictionary for consecutive value-keys
# Using dictionary comprehension + accumulate()
from itertools import accumulate

# initializing dictionary
test_dict = {1 : 3, 4 : 5, 3 : 4, 5 : 6}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Rearrange dictionary for consecutive value-keys
# Using dictionary comprehension + accumulate()
res = {key : test_dict[key] for key in accumulate(test_dict,
                              lambda key, x :test_dict[key])}

# printing result
print("The rearranged dictionary : " + str(res))
```

**Output : **

```py
The original dictionary : {1: 3, 4: 5, 3: 4, 5: 6}
The rearranged dictionary : {1: 3, 3: 4, 4: 5, 5: 6}
```