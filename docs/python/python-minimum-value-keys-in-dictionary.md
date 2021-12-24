# Python |字典中的最小值键

> 原文:[https://www . geesforgeks . org/python-字典中的键值最小值/](https://www.geeksforgeeks.org/python-minimum-value-keys-in-dictionary/)

很多时候，我们可能会遇到这样的问题，我们不仅需要找到值，还需要找到整个字典中最小值的对应键。让我们讨论执行这项任务的某些方法。

**方法#1:使用 min() +列表理解+值()**
以上功能的组合可用于执行此特定任务。在这种情况下，最小值使用`min`函数提取，而字典的值使用`values()`提取。列表理解用于迭代字典以匹配具有最小值的关键字。

```py
# Python3 code to demonstrate working of
# Finding min value keys in dictionary
# Using min() + list comprehension + values()

# initializing dictionary
test_dict = {'Gfg' : 11, 'for' : 2, 'CS' : 11, 'geeks':8, 'nerd':2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using min() + list comprehension + values()
# Finding min value keys in dictionary
temp = min(test_dict.values())
res = [key for key in test_dict if test_dict[key] == temp]

# printing result 
print("Keys with minimum values are : " + str(res))
```

**Output:**

> 最初的字典是:{'nerd': 2，' Gfg': 11，' geeks': 8，' CS': 11，' for': 2}
> 最小值的键是:['nerd '，' for']