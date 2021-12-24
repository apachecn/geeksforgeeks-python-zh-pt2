# Python–字典中排序的嵌套键

> 原文:[https://www . geesforgeks . org/python-sorted-nested-key-in-dictionary/](https://www.geeksforgeeks.org/python-sorted-nested-keys-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要提取嵌套字典的所有键，并按排序顺序呈现它们。这种应用可以出现在我们处理数据的领域中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 yield + isinstance() + loop**
以上函数的组合可以用来执行这个任务。在本例中，我们使用 isinstance()执行密钥检测任务。yield 关键字用于添加中间结果。

```
# Python3 code to demonstrate working of 
# Sorted Nested Keys in Dictionary
# Using yield + isinstance() + loop

def hlper_fnc(test_dict):
     for key, val in test_dict.items():
         yield key
         if isinstance(val, dict):
             yield from val

# initializing dictionary
test_dict = {'gfg': 43, 'is': {'best' : 14, 'for' : 35, 'geeks' : 42}, 'and' : {'CS' : 29}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sorted Nested Keys in Dictionary
# Using yield + isinstance() + loop
res = sorted(hlper_fnc(test_dict))

# printing result 
print("The sorted nested keys : " + str(res)) 
```

**Output :**

> 原始字典为:{'and': {'CS': 29}，' gfg': 43，' is': {'for': 35，' best': 14，' geeks': 42}}
> 排序后的嵌套键:['CS '，' and '，' best '，' for '，' geeks '，' gfg '，' is']