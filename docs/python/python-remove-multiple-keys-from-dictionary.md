# Python |从字典中移除多个键

> 原文:[https://www . geesforgeks . org/python-remove-multi-key-from-dictionary/](https://www.geeksforgeeks.org/python-remove-multiple-keys-from-dictionary/)

在使用 Python 字典时，我们可以使用一个实用程序，在该程序中，我们需要一次删除多个键。在使用 NoSQL 数据库进行网络开发时，可能会出现这种问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`pop()` +列表理解**
在该方法中，我们只使用 pop 函数，该函数用于移除单个键以及对整个列表迭代的列表理解来执行移除操作。

```py
# Python3 code to demonstrate working of
# Remove multiple keys from dictionary
# Using pop() + list comprehension

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5}

# initializing Remove keys
rem_list = ['is', 'for', 'CS']

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using pop() + list comprehension
# Remove multiple keys from dictionary
[test_dict.pop(key) for key in rem_list]

# printing result 
print("Dictionary after removal of keys : " + str(test_dict))
```

**Output :**

> 原始字典为:{'is': 2，' best': 3，' for': 4，' Gfg': 1，' CS': 5}
> 删除键后的字典:{'best': 3，' Gfg': 1}