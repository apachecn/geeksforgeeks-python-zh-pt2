# Python |字典中关键字的值求和

> 原文:[https://www . geesforgeks . org/python-value-summary-of-key-in-dictionary/](https://www.geeksforgeeks.org/python-value-summation-of-key-in-dictionary/)

使用 Python 字典可以进行许多操作，如分组和转换。但是有时候，我们也会遇到一个问题，那就是我们需要对字典列表中的键值进行聚合。这个任务在日常编程中很常见。让我们讨论执行这项任务的某些方法。

**方法一:使用 `sum()` +列表理解**

这是一种线性方法，用于执行获取特定键的和的任务，同时使用列表理解迭代字典列表中的相似键。

```py
# Python3 code to demonstrate working of
# Value summation of key in dictionary
# Using sum() + list comprehension

# Initialize list
test_list = [{'gfg' : 1, 'is' : 2, 'best' : 3},
             {'gfg' : 7, 'is' : 3, 'best' : 5},
             {'gfg' : 9, 'is' : 8, 'best' : 6}] 

# printing original list
print("The original list is : " + str(test_list))

# Value summation of key in dictionary
# Using sum() + list comprehension
res = sum(sub['gfg'] for sub in test_list)

# printing result
print("The sum of particular key is : " + str(res))
```

**Output :**

> 原始列表为:[{'best': 3，' gfg': 1，' is': 2}，{'best': 5，' gfg': 7，' is': 3}，{'best': 6，' gfg': 9，' is': 8}]
> 特定键的和为:17

**方法 2:使用`sum() + itemgetter() + map()`**
这些功能的组合也可以用来执行这个任务。在这一点上，主要区别在于理解任务由`map()`完成，关键访问任务由`itemgetter().`完成

```py
# Python3 code to demonstrate working of
# Value summation of key in dictionary
# Using sum() + itemgetter() + map()
import operator

# Initialize list
test_list = [{'gfg' : 1, 'is' : 2, 'best' : 3},
             {'gfg' : 7, 'is' : 3, 'best' : 5},
             {'gfg' : 9, 'is' : 8, 'best' : 6}] 

# printing original list
print("The original list is : " + str(test_list))

# Value summation of key in dictionary
# Using sum() + itemgetter() + map()
res = sum(map(operator.itemgetter('gfg'), test_list))

# printing result
print("The sum of particular key is : " + str(res))
```

**Output :**

> 原始列表为:[{'best': 3，' gfg': 1，' is': 2}，{'best': 5，' gfg': 7，' is': 3}，{'best': 6，' gfg': 9，' is': 8}]
> 特定键的和为:17