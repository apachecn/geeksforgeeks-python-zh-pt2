# Python–从字典中移除顶层

> 原文:[https://www . geesforgeks . org/python-remove-top-level-from-dictionary/](https://www.geeksforgeeks.org/python-remove-top-level-from-dictionary/)

有时，在使用 Python Dictionaries 时，我们可以使用字典嵌套，每个键都是单值字典。在这种情况下，我们需要删除字典的顶层。这可以在数据预处理中得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`values()` +字典理解**
以上功能的组合可以解决这个问题。在这种情况下，我们使用字典理解执行字典重建任务，并使用值()提取嵌套列表。

```py
# Python3 code to demonstrate working of 
# Remove Top level from Dictionary
# Using dictionary comprehension + values()

# initializing dictionary
test_dict = {'gfg' : {'data1' : [4, 5, 6, 7]},
             'is' : {'data2' : [1, 3, 8]},
             'best' : {'data3' : [9, 10, 13]}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Remove Top level from Dictionary
# Using dictionary comprehension + values()
res = dict(ele for sub in test_dict.values() for ele in sub.items())

# printing result 
print("The top level removed dictionary is : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': {'data2': [1，3，8]}，' gfg': {'data1': [4，5，6，7]}，' best': {'data3': [9，10，13]}}
> 移除的顶级字典为:{'data1': [4，5，6，7]，' data2': [1，3，8]，' data3': [9，10，13]}