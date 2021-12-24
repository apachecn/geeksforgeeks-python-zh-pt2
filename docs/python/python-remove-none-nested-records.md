# Python–删除无嵌套记录

> 原文:[https://www . geesforgeks . org/python-remove-non-nested-records/](https://www.geeksforgeeks.org/python-remove-none-nested-records/)

有时，在使用 Python Records 时，可能会出现这样的问题:我们需要删除嵌套记录中所有键值都为“无”的数据。这类问题可以在数据预处理中得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`all()` +词典理解**
以上功能的组合可以用来解决这个问题。在这种情况下，使用 all()移除字典重新构造中不包含的所有无值的所有值。

```py
# Python3 code to demonstrate working of 
# Remove None Nested Records
# Using all() + dictionary comprehension

# initializing dictionary
test_dict = {'gfg' : {'a' : 1, 'b' : 2}, 
              'is' : {'d' : None, 'e' : None}, 
              'best' : {'g' : 1}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Remove None Nested Records
# Using all() + dictionary comprehension
res = {key: sub1 for key, sub1 in test_dict.items() if not
      all(sub2 is None for sub2 in sub1.values())}

# printing result 
print("The dictionary after removal : " + str(res)) 
```

**Output :**

> 原词典为:{'gfg': {'b': 2，' a': 1}，' is': {'e ':无'，' d ':无'，' best': {'g': 1}}
> 删除后的词典:{'gfg': {'b': 2，' a': 1}，' best': {'g': 1}}