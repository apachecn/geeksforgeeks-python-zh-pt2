# Python–跨字典值删除重复值

> 原文:[https://www . geesforgeks . org/python-remove-replicate-values-trans-dictionary-values/](https://www.geeksforgeeks.org/python-remove-duplicate-values-across-dictionary-values/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要删除所有字典值列表中的所有重复值。这个问题在数据领域和 web 开发领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'Manjeet': [1]，' Akash': [1，8，9]}
> **输出** : {'Manjeet': []，' Akash': [8，9]}
> 
> **输入** : test_dict = {'Manjeet': [1，1，1]，' Akash': [1，1，1]}
> **输出** : {'Manjeet': []，' Akash': []}

**方法一:使用`Counter()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 Counter()来提取所有频率，并使用列表理解来分配值列表中出现一次的值。

```py
# Python3 code to demonstrate working of 
# Remove duplicate values across Dictionary Values
# Using Counter() + list comprehension
from collections import Counter

# initializing dictionary
test_dict = {'Manjeet' : [1, 4, 5, 6],
            'Akash' : [1, 8, 9],
            'Nikhil': [10, 22, 4],
            'Akshat': [5, 11, 22]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Remove duplicate values across Dictionary Values
# Using Counter() + list comprehension
cnt = Counter()
for idx in test_dict.values():
    cnt.update(idx)
res = {idx: [key for key in j if cnt[key] == 1] 
               for idx, j in test_dict.items()}

# printing result 
print("Uncommon elements records : " + str(res)) 
```

**Output :**

> 原词典:{'Akshat': [5，11，22]，' Nikhil': [10，22，4]，' Manjeet': [1，4，5，6]，' Akash': [1，8，9]}
> 不常见元素记录:{'Akshat': [11]，' Nikhil': [10]，' Manjeet': [6]，' Akash': [8，9]}