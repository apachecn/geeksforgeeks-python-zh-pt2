# Python |按键排序嵌套字典

> 原文:[https://www . geesforgeks . org/python-sort-nested-dictionary-by-key/](https://www.geeksforgeeks.org/python-sort-nested-dictionary-by-key/)

排序有非常生动的应用，有时，我们可能会遇到这样的问题，即我们需要按嵌套键对嵌套字典进行排序。这种类型的应用程序在 web 开发中很流行，因为 JSON 格式非常流行。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`OrderedDict() + sorted()`**

这个任务可以使用 OrderedDict 函数来执行，该函数将字典转换为其参数中提到的特定顺序，该参数由排序函数操作，以便根据传递的键值进行排序。

```
# Python3 code to demonstrate
# Sort nested dictionary by key
# using OrderedDict() + sorted()
from collections import OrderedDict
from operator import getitem

# initializing dictionary
test_dict = {'Nikhil' : { 'roll' : 24, 'marks' : 17},
             'Akshat' : {'roll' : 54, 'marks' : 12}, 
             'Akash' : { 'roll' : 12, 'marks' : 15}}

# printing original dict
print("The original dictionary : " + str(test_dict))

# using OrderedDict() + sorted()
# Sort nested dictionary by key
res = OrderedDict(sorted(test_dict.items(),
       key = lambda x: getitem(x[1], 'marks')))

# print result
print("The sorted dictionary by marks is : " + str(res))
```

**Output :**

> 原始字典:{'Nikhil': {'roll': 24，' marks': 17}，' Akash': {'roll': 12，' marks': 15}，' Akshat': {'roll': 54，' marks': 12}}
> 按标记排序的字典为:OrderedDict([('Akshat '，{'roll': 54，' marks': 12})，(' Akash '，{'roll': 12，' marks': 15})，(' Nikhil '，{'roll': 12

**方法 2:使用`sorted()`**

如果我们只使用 sorted 函数，我们可以更好地实现上面的结果，因为它以更有用的格式返回结果，dict 并精确地执行期望的任务。

```
# Python3 code to demonstrate
# Sort nested dictionary by key
# using sorted()

# initializing dictionary
test_dict = {'Nikhil' : { 'roll' : 24, 'marks' : 17},
             'Akshat' : {'roll' : 54, 'marks' : 12}, 
             'Akash' : { 'roll' : 12, 'marks' : 15}}

# printing original dict
print("The original dictionary : " + str(test_dict))

# using sorted()
# Sort nested dictionary by key
res = sorted(test_dict.items(), key = lambda x: x[1]['marks'])

# print result
print("The sorted dictionary by marks is : " + str(res))
```

**Output :**

> 原版字典:{'Nikhil': {'marks': 17，' roll': 24}，' Akshat': {'marks': 12，' roll': 54}，' Akash': {'marks': 15，' roll': 12}}
> 按标记排序的字典为:[('Akshat '，{'marks': 12，' roll': 54})，(' Akash '，{'marks': 15，' roll': 12})，(' Nikhil '，{'marks': 17，' roll