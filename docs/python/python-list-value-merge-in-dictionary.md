# Python |字典中的列表值合并

> 原文:[https://www . geesforgeks . org/python-list-value-merge-in-dictionary/](https://www.geeksforgeeks.org/python-list-value-merge-in-dictionary/)

有时，在使用字典时，我们会遇到一个问题，即我们有许多字典，并且我们需要像键一样进行合并。这个问题看起来很常见，但复杂的是如果键值是 list，我们需要向相似键的列表中添加元素。让我们讨论一下解决这个问题的方法。

**方法:使用列表理解+ `items()`**
这个问题可以通过使用列表理解来解决，该列表理解可以用于合并列表内容，还可以使用`items`方法来获取字典键和值。

```py
# Python3 code to demonstrate working of
# List value merge in dictionary
# Using items() + list comprehension

# initializing dictionaries
test_dict1 = {'Gfg' : [1, 2, 3], 'for' : [2, 4], 'CS' : [7, 8]}
test_dict2 = {'Gfg' : [10, 11], 'for' : [5], 'CS' : [0, 18]}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Using items() + list comprehension
# List value merge in dictionary
res = {key: value + test_dict2[key] for key, value in test_dict1.items()}

# printing result 
print("The merged dictionary is : " + str(res))
```

**Output :**

> 原始字典 1 为:{'for': [2，4]，' CS': [7，8]，' Gfg': [1，2，3]}
> 原始字典 2 为:{'for': [5]，' CS': [0，18]，' Gfg': [10，11]}
> 合并字典为:{'for': [2，4，5]，' CS': [7，8，0，18]，' Gfg': [1，2，3，10，11