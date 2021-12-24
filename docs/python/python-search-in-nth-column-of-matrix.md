# Python |矩阵第 n 列搜索

> 原文:[https://www . geesforgeks . org/python-矩阵第 n 列搜索/](https://www.geeksforgeeks.org/python-search-in-nth-column-of-matrix/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，需要检查元素是否存在。这个问题比较简单，但是它的一个变体可以是在矩阵的特定列中执行检查。让我们讨论一下执行这项任务的速记方法。

**方法:使用`any()` +列表理解**
该任务可以使用上述功能的组合来执行，其中我们暗示对迭代和支持任务的列表理解，并且`any()`可以用于检查所需字符的任何出现。

```
# Python3 code to demonstrate working of
# Search in Nth Column of Matrix
# Using any() + list comprehension

# initializing list 
test_list = [[1, 4, 5], [6, 7, 8], [8, 3, 0]]

# printing list 
print("The original list : " + str(test_list))

# initializing N 
N = 1 

# initializing num
ele = 3

# Search in Nth Column of Matrix
# Using any() + list comprehension
res = any(sub[N] == ele for sub in test_list)

# Printing result
print("Does element exists in particular column : " + str(res))
```

**Output :**

```

The original list : [[1, 4, 5], [6, 7, 8], [8, 3, 0]]
Does element exists in particular column : True

```