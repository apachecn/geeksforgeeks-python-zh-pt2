# Python |合并 Python 键值列表

> 原文:[https://www . geesforgeks . org/python-merge-python-key-values-to-list/](https://www.geeksforgeeks.org/python-merge-python-key-values-to-list/)

有时候，在使用 Python 时，我们可能会遇到一个问题，我们需要从几个字典中获取字典的值，并将其封装到一个字典中。这种类型的问题在我们处理关系数据的领域很常见，比如在 web 开发中。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`setdefault()` +循环**
这个任务可以使用嵌套循环来执行，并获取字典的每个元素，并为新关键字创建一个新列表，或者在出现类似关键字的情况下追加值。

```
# Python3 code to demonstrate working of
# Merge Python key values to list
# Using setdefault() + loop

# Initialize list
test_list = [{'gfg' : 2, 'is' : 4, 'best' : 6}, 
             {'it' : 5, 'is' : 7, 'best' : 8},
             {'CS' : 10}]

# Printing original list
print("The original list is : " + str(test_list))

# using setdefault() + loop
# Merge Python key values to list
res = {}
for sub in test_list:
    for key, val in sub.items(): 
        res.setdefault(key, []).append(val)

# printing result 
print("The merged values encapsulated dictionary is : " + str(res))
```

**Output :**

> 原始列表为:[{'is': 4，' gfg': 2，' best': 6}，{'it': 5，' is': 7，' best': 8}，{'CS': 10}]
> 合并值封装字典为:{'is': [4，7]，' it': [5]，' gfg': [2]，' CS': [10]，' best': [6，8]}