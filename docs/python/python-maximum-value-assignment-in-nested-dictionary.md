# Python–嵌套字典中的最大值赋值

> 原文:[https://www . geesforgeks . org/python-最大值-嵌套赋值-字典/](https://www.geeksforgeeks.org/python-maximum-value-assignment-in-nested-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要分配给外部键，即内部键中具有最大值的项。这种问题可能发生在日常编程和 web 开发领域。让我们讨论一下执行这项任务的方法。

> **输入**:test _ dict = { ' Manjeet ':{ ' English ':19，'数学系':1}，' Himani': {'English': 18，'数学系':17}}
> **输出** : [{'Manjeet': ('English '，19)}，{'Himani': ('English '，18)}]
> 
> **输入** : test_dict = {'Manjeet' : { '数学':10}}
> **输出** : [{'Manjeet ':('数学'，10)}]

**方法:使用`Counter().most_common() + items()` +循环**
以上功能的组合构成了解决这个问题的蛮法。在本例中，我们使用 most_common()提取最大元素，items()用于提取键值对。

```
# Python3 code to demonstrate working of 
# Maximum value assignment in Nested Dictionary
# Using Counter().most_common() + items() + loop
from collections import Counter

# initializing dictionary
test_dict = {'Manjeet' : {'Maths':1, 'English':0, 'Physics':2, 'Chemistry':3},
            'Akash' : {'Maths':0, 'English':0, 'Physics':3, 'Chemistry':2},
            'Nikhil': {'Maths':4, 'English':2, 'Physics':2, 'Chemistry':3},
            'Akshat': {'Maths':1, 'English':0, 'Physics':2, 'Chemistry':0}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Maximum value assignment in Nested Dictionary
# Using Counter().most_common() + items() + loop
res = []
for key, val in test_dict.items():
    cnt = Counter(val)
    res.append({key : cnt.most_common(1)[0]})

# printing result 
print("Maximum element key : " + str(res)) 
```

**Output :**

> 原版词典:{'Nikhil': {'Chemistry': 3，' Physics': 2，'数学系':4，' English ':{ Chemistry ':2，' Physics': 3，'数学系':0，' English ':{ ' Chemistry ':0 '，' Akshat': {'Chemistry': 0 '，' Physics': 2 '，' English': 0}}
> 
> 最大元素键:[{ ' Nikhil ':(' mathematics '，4)}，{'Akash': ('Physics '，3)}，{'Akshat': ('Physics '，2)}，{'Manjeet': ('Chemistry '，3)}]