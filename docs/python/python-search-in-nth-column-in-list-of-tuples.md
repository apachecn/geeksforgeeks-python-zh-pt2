# Python |元组列表第 n 列搜索

> 原文:[https://www . geeksforgeeks . org/python-在元组列表中搜索第 n 列/](https://www.geeksforgeeks.org/python-search-in-nth-column-in-list-of-tuples/)

有时，在使用 Python 列表时，我们可能会有一个由元组组成的数据集，并且我们遇到了一个问题，即我们需要在列表的第 N 列中搜索元素。这在网络开发领域有它的应用。让我们讨论执行这项任务的某些方法。

**方法:使用`enumerate()` +列表理解**
在该技术中，我们使用 enumerate()的能力在单次迭代中访问索引和值，然后在列表理解的帮助下，我们构建一个条件语句，在该语句中我们检查给定列中的有效值。

```
# Python3 code to demonstrate working of
# Search in Nth column in list of tuples
# Using enumerate() + list comprehension

# initializing list 
test_list = [('gfg', 1, 9), ('is', 5, 10), (8, 'best', 13)]

# printing list 
print("The original list : " + str(test_list))

# initializing Nth column
N = 2

# initializing num 
ele = 10

# Search in Nth column in list of tuples
# Using enumerate() + list comprehension
res = [idx for idx, val in enumerate(test_list) if val[N] == ele]

# Printing result
print("Row of desired element is : " + str(res))
```

**Output :**

```

The original list : [('gfg', 1, 9), ('is', 5, 10), (8, 'best', 13)]
Row of desired element is : [1]

```