# Python |拆分展平字符串列表

> 原文:[https://www . geesforgeks . org/python-split-flat-string-list/](https://www.geeksforgeeks.org/python-split-flatten-string-list/)

有时，在使用 Python Strings 时，我们可能会遇到这样的问题，即需要在特定的交付器上执行字符串拆分。在这种情况下，我们可能需要将其展平为单个字符串列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `split() + extend()`**
以上功能的组合可以用来执行这个任务。在本例中，我们使用 split()执行拆分任务，并使用 extend()在列表中添加拆分元素。

```py
# Python3 code to demonstrate working of 
# Split flatten String List
# Using list comprehension + split() + extend()

# initializing list
test_list = ['gfg-is-best', 'for-all', 'geeks-and', 'CS']

# printing original list
print("The original list is : " + str(test_list))

# Split flatten String List
# Using list comprehension + split() + extend()
res = []
[res.extend(idx.split("-")) for idx in test_list] 

# printing result 
print("The String List after extension : " + str(res)) 
```

**Output :**

```py
The original list is : ['gfg-is-best', 'for-all', 'geeks-and', 'CS']
The String List after extension : ['gfg', 'is', 'best', 'for', 'all', 'geeks', 'and', 'CS']

```