# Python–按值差排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-value-difference/](https://www.geeksforgeeks.org/python-sort-dictionary-by-value-difference/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即我们需要根据各种因素对项目进行排序。一个这样的可以基于双值列表的绝对差异。这可能发生在 Python > 3.6 中，因为字典是有序的。这种问题会出现在数据领域。让我们讨论一下解决这个问题的方法。

**方法:使用`sorted() + lambda + abs()` +字典理解**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 sorted()执行排序任务，lambda 函数用于提供逻辑，abs()函数用于计算绝对差值。

```
# Python3 code to demonstrate working of 
# Sort Dictionary by Value Difference
# Using sorted() + lambda + abs() + dictionary comprehension

# initializing dictionary
test_dict = {'gfg' : [34, 87],
              'is' : [10, 13], 
              'best' : [19, 27], 
              'for' : [10, 50], 
              'geeks' : [15, 45]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sort Dictionary by Value Difference
# Using sorted() + lambda + abs() + dictionary comprehension
res = dict(sorted(test_dict.items(), key = lambda sub: abs(sub[1][0] - sub[1][1])))

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output :**

> 原字典为:{'gfg': [34，87]，' is': [10，13]，' best': [19，27]，' for': [10，50]，' geeks': [15，45]}
> 排序后的字典:{'is': [10，13]，' best': [19，27]，' geeks': [15，45]，' for': [10，50]，' gfg': [34，87