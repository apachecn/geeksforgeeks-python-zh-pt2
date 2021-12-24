# Python |从嵌套词典中删除重复词典

> 原文:[https://www . geesforgeks . org/python-remove-replica-dictionary-from-nested-dictionary/](https://www.geeksforgeeks.org/python-remove-duplicate-dictionaries-from-nested-dictionary/)

给定一个嵌套字典，任务是从字典中删除重复的字典。下面给出了完成给定任务的几种方法。

**方法#1:使用朴素方法**

```
# Python code to demonstrate
# for removing duplicate values from dictionary

# initialising dictionary
ini_dict = {'a':{'b':1, 'c':2}, 'b':{'b':1, 'c':2}, 
            'c':{'a':2, 'b':3}, 'd':{'a':2, 'b':7}}

# printing initial_dictionary
print ("initial dictionary", str(ini_dict))

# code to remove duplicates
result = {}

for key, value in ini_dict.items():
    if value not in result.values():
        result[key] = value

# printing result
print ("result", str(result))
```

**Output:**

> 初始字典{'c': {'a': 2，' b': 3}，' d': {'a': 2，' b': 7}，' a': {'c': 2，' b': 1}，' b': {'c': 2，' b': 1}}
> 结果{'c': {'a': 2，' b': 3}，' d': {'a': 2，' b': 7}，' a': {'c': 2，' b': 1}}