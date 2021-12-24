# Python–奇频字符

> 原文:[https://www . geesforgeks . org/python-奇数频率-字符/](https://www.geeksforgeeks.org/python-odd-frequency-characters/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要提取出现次数为奇数的所有字符串。这个问题可以应用于数据域和日常编程等领域。让我们讨论执行这项任务的某些方法。

> **输入**:test _ str = ' geek forkeks '
> **输出** : ['r '，' o '，' f '，' s']
> 
> **输入** : test_str = 'g'
> **输出** : ['g']

**方法一:使用`defaultdict()` +列表理解+循环**
以上功能的组合可以解决这个问题。在本文中，我们用整数初始化 defaultdict()，然后执行频率计数。列表理解用于提取所有奇数频率。

```
# Python3 code to demonstrate working of 
# Odd Frequency Characters
# Using list comprehension + defaultdict()
from collections import defaultdict

# helper_function
def hlper_fnc(test_str):
    cntr = defaultdict(int)
    for ele in test_str:
        cntr[ele] += 1
    return [val for val, chr in cntr.items() if chr % 2 != 0]

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# Odd Frequency Characters
# Using list comprehension + defaultdict()
res = hlper_fnc(test_str)

# printing result 
print("The Odd Frequency Characters are : " + str(res))
```

**Output :**

```
The original string is : geekforgeeks is best for geeks
The Odd Frequency Characters are : ['k', 'i', 't', 'g', 'e', 'b']

```

**方法 2:使用列表理解+ `Counter()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 Counter()来计算频率。

```
# Python3 code to demonstrate working of 
# Odd Frequency Characters
# Using list comprehension + Counter()
from collections import Counter

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# Odd Frequency Characters
# Using list comprehension + Counter()
res =  [ chr for chr, count in Counter(test_str).items() if count & 1 ]

# printing result 
print("The Odd Frequency Characters are : " + str(res))
```

**Output :**

```
The original string is : geekforgeeks is best for geeks
The Odd Frequency Characters are : ['k', 'i', 't', 'g', 'e', 'b']

```