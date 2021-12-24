# Python |选择键求和

> 原文:[https://www . geesforgeks . org/python-selected-key-summary/](https://www.geeksforgeeks.org/python-selective-keys-summation/)

有时候，在使用 Python 字典时，我们可能会遇到一个问题，那就是我们需要对字典中的选择性键值进行求和。这个问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `get() + sum()`**
以上功能的组合可以用来执行这个特定的任务。在本文中，我们使用 get 方法访问值，并使用列表理解遍历字典。我们使用 sum()执行求和。

```py
# Python3 code to demonstrate working of 
# Selective Keys Summation
# Using list comprehension + get() + sum() 

# Initialize dictionary 
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5} 

# printing original dictionary 
print("The original dictionary : " + str(test_dict)) 

# Initialize key list 
key_list = ['gfg', 'best', 'CS'] 

# Using list comprehension + get() + sum()
# Selective Keys Summation
res = sum([test_dict.get(key) for key in key_list]) 

# printing result 
print("The summation of Selective keys : " + str(res)) 
```

**Output :**

```py
The original dictionary : {'CS': 5, 'best': 3, 'is': 2, 'gfg': 1, 'for': 4}
The summation of Selective keys : 9

```