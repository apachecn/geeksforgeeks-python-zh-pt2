# Python |元组列表中第 n 个索引的最小 K 条记录

> 原文:[https://www . geesforgeks . org/python-minimum-k-records-of-n-index-in-tuple-list/](https://www.geeksforgeeks.org/python-minimum-k-records-of-nth-index-in-tuple-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要获取由记录的第 n 个元素过滤的最少元素。这在 web 开发领域有着非常重要的用途。让我们讨论执行这项任务的某些方法。

**方法#1:使用`filter() + lambda + set()` +列表理解**
以上功能的组合可用于执行该特定功能。在这种情况下，我们首先从第 n 个索引中过滤最小的 K 个元素，然后将这些值应用于列表并返回结果。

```
# Python3 code to demonstrate working of
# Minimum K records of Nth index in tuple list
# Using filter() + lambda + set() + list comprehension

# initialize list 
test_list = [('gfg', 4, 'good'), ('gfg', 2, 'better'), 
              ('gfg', 1, 'best'), ('gfg', 3, 'geeks')]

# printing original list
print("The original list is : " + str(test_list))

# initialize N 
N = 1

# initialize K 
K = 2

# Minimum K records of Nth index in tuple list
# Using filter() + lambda + set() + list comprehension
temp = set(list({sub[N] for sub in test_list})[ :K])
res = list(filter(lambda sub: sub[N] in temp, test_list))

# printing result
print("Min K elements of Nth index are : " + str(res))
```

**Output :**

> 原列表为:[('gfg '，4，' good ')，(' gfg '，2，' better ')，(' gfg '，1，' best ')，(' gfg '，3，' geeks')]
> 第 n 个索引的 Min K 元素为:[('gfg '，2，' better ')，(' gfg '，1，' best')]