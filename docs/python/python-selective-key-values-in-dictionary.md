# Python |字典中的选择性键值

> 原文:[https://www . geesforgeks . org/python-选择性-关键字-字典中的值/](https://www.geeksforgeeks.org/python-selective-key-values-in-dictionary/)

有时候，在使用 Python 字典时，我们可能会遇到一个问题，我们需要从字典中获取选择性键值。这个问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `get()`**
以上功能的组合可以用来执行这个特定的任务。在这种情况下，我们使用 `get`方法访问值，并使用列表理解遍历字典。

```py
# Python3 code to demonstrate working of
# Selective key values in dictionary
# Using list comprehension + get()

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize key list 
key_list = ['gfg', 'best', 'CS']

# Using list comprehension + get()
# Selective key values in dictionary
res = [test_dict.get(key) for key in key_list]

# printing result 
print("The values of Selective keys : " + str(res))
```

**Output :**

> 原始字典:{'is': 2，' gfg': 1，' for': 4，' CS': 5，' best': 3}
> 选择性键的值:[1，3，5]