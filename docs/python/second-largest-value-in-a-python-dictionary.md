# Python 字典中的第二大值

> 原文:[https://www . geesforgeks . org/第二大 python 字典中的值/](https://www.geeksforgeeks.org/second-largest-value-in-a-python-dictionary/)

在这个问题中，我们将在给定的字典中找到第二大值。
**例:**

```
Input :  {'one':5, 'two':1, 'three':6, 'four':10}
Output :  Second largest value of the dictionary is 6

Input :   {1: 'Geeks', 'name': 'For', 3: 'Geeks'}
Output :  Second largest value of the dictionary is Geeks

```

```
dictionary = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}
val = list(dictionary.values())
val.sort()
res = val[-2]
print(res)
```

**Output:**

```
Geeks

```

时间复杂度:0(对数 n)

更多方法请参考下面的帖子:

[Python 程序在字典中查找第二个最大值](https://www.geeksforgeeks.org/python-program-to-find-second-maximum-value-in-dictionary/)