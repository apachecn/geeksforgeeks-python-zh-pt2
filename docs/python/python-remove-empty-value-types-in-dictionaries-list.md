# Python–删除字典列表中的空值类型

> 原文:[https://www . geesforgeks . org/python-remove-empty-value-type-in-dictionary-list/](https://www.geeksforgeeks.org/python-remove-empty-value-types-in-dictionaries-list/)

有时，在使用 Python 字典时，我们要求移除所有实际上为空的值，即不包含任何有意义的值，并且要在处理数据之前移除，这可以是空字符串、空列表、字典甚至是 0。这在数据预处理中有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是执行这项任务的暴力方式的简写。在这种情况下，我们只使用有效值重新构建字典。

```
# Python3 code to demonstrate working of 
# Remove None value types in dictionaries list
# Using list comprehension

# initializing list
test_list = [{'gfg' : 4, 'is' : '', 'best' : []}, {'I' : {}, 'like' : 5, 'gfg' : 0}]

# printing original list
print("The original list is : " + str(test_list))

# Remove None value types in dictionaries list
# Using list comprehension
res = [ele for ele in ({key: val for key, val in sub.items() if val} for sub in test_list) if ele]

# printing result 
print("The filtered list : " + str(res)) 
```

**Output :**

```
The original list is : [{'is': '', 'best': [], 'gfg': 4}, {'like': 5, 'gfg': 0, 'I': {}}]
The filtered list : [{'gfg': 4}, {'like': 5}]

```