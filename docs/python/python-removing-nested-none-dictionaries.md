# Python–移除嵌套的无词典

> 原文:[https://www . geesforgeks . org/python-remove-nested-none-dictionary/](https://www.geeksforgeeks.org/python-removing-nested-none-dictionaries/)

有时，在使用记录时，我们会遇到一个问题，即需要从字典中移除嵌套的空记录。这可以在数据预处理中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`dict() + filter()`**
这是可以执行这个任务的方式之一。在本例中，我们使用过滤器()执行过滤无值的任务。

```py
# Python3 code to demonstrate working of 
# Removing Nested None Dictionaries
# Using filter() + dict()

# initializing dictionary
test_dict = {'gfg' : {'a': 5}, 'best' : {}, 'for' : {}, 'geeks' : {'b' : 6}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Removing Nested None Dictionaries
# Using filter() + dict()
res = dict(filter(lambda sub: sub[1], test_dict.items()))

# printing result 
print("The dictionary after filtering is : " + str(res)) 
```

**Output :**

> 原词典为:{'geeks': {'b': 6}、' for': {}、' gfg': {'a': 5}、' best ':{ }
> 筛选后的词典为:{'geeks': {'b': 6}、' gfg': {'a': 5}}