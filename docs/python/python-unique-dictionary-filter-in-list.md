# Python |列表中唯一的字典过滤器

> 原文:[https://www . geesforgeks . org/python-unique-dictionary-filter-in-list/](https://www.geeksforgeeks.org/python-unique-dictionary-filter-in-list/)

在使用 Python 字典时，我们总是会遇到一个问题，即我们有可能重复的字典列表，我们希望删除重复的字典。这是机器学习领域中一个常见的问题。让我们讨论一下解决这个问题的某些方法。

**方法:使用`map() + set() + items() + sorted() + tuple()`**

在这个方法中，我们只是组合函数来执行这个任务。`map`功能执行将逻辑扩展到所有元素的任务。`set`功能对`items()`访问的对进行实际过滤。设置需要`sorted`功能来删除重复。

```
# Python3 code to demonstrate working of
# Unique dictionary filter in list
# Using map() + set() + items() + sorted() + tuple()

# Initialize list
test_list = [{'gfg' : 1, 'is' : 2, 'best' : 3},
             {'gfg' : 1, 'is' : 2, 'best' : 3},
             {'gfg' : 9, 'is' : 8, 'best' : 6}] 

# printing original list
print("The original list is : " + str(test_list))

# Unique dictionary filter in list
# Using map() + set() + items() + sorted() + tuple()
res = list(map(dict, set(tuple(sorted(sub.items())) for sub in test_list)))

# printing result
print("The list after removing duplicates : " + str(res))
```

**Output :**

> 原始列表为:[{'gfg': 1，' is': 2，' best': 3}，{'gfg': 1，' is': 2，' best': 3}，{'gfg': 9，' is': 8，' best': 6}]
> 删除重复项后的列表:[{'gfg': 1，' is': 2，' best': 3}，{'gfg': 9，' is': 8，' best': 6}]