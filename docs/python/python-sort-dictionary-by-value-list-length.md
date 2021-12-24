# Python |按值列表长度排序字典

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-by-value-list-length/](https://www.geeksforgeeks.org/python-sort-dictionary-by-value-list-length/)

使用 Python 时，可能会遇到一个问题，需要对字典列表值长度执行排序。这通常是在计分或任何类型的计数算法的情况下。让我们讨论一种执行这项任务的方法。

**方法:使用`sorted() + join()` + lambda**
上述功能的组合可用于执行该特定任务。在这里，我们只使用 lambda 函数来执行这个特定的任务，`sorted`和`join`函数分别执行所需的结果排序和封装。

```py
# Python3 code to demonstrate working of
# Sort dictionary by value list length
# using sorted() + join() + lambda

# Initialize dictionary
test_dict = {'is' : [1, 2], 'gfg' : [3], 'best' : [1, 3, 4]}

# Printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using sorted() + join() + lambda
# Sort dictionary by value list length
res = ' '.join(sorted(test_dict, key = lambda key: len(test_dict[key])))

# printing result 
print("Sorted keys by value list : " + res)
```

**Output :**

```py
The original dictionary is : {'is': [1, 2], 'best': [1, 3, 4], 'gfg': [3]}
Sorted keys by value list : gfg is best

```