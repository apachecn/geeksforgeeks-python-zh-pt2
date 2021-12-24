# Python–字典中过滤关键字的最大数量

> 原文:[https://www . geesforgeks . org/python-字典中最大过滤键数/](https://www.geeksforgeeks.org/python-maximum-of-filtered-keys-in-dictionary/)

有时在使用 Python 字典时，我们可能会遇到一个问题，即我们需要从字典中最大化选择性键值。这个问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `get() + max()`**
以上功能的组合可以用来执行这个特定的任务。在本文中，我们使用 get 方法访问值，并使用列表理解遍历字典。我们使用 max()执行最大化。

```
# Python3 code to demonstrate working of 
# Maximum of filtered Keys
# Using list comprehension + get() + max() 

# Initialize dictionary 
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5} 

# printing original dictionary 
print("The original dictionary : " + str(test_dict)) 

# Initialize key list 
key_list = ['gfg', 'best', 'CS'] 

# Using list comprehension + get() + max() 
# Maximum of filtered Keys
res = max([test_dict.get(key) for key in key_list]) 

# printing result 
print("The maximum of Selective keys : " + str(res)) 
```

**Output :**

```
The original dictionary : {'for': 4, 'gfg': 1, 'is': 2, 'best': 3, 'CS': 5}
The maximum of Selective keys : 5

```