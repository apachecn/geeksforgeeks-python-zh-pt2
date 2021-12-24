# Python |将字典值乘以常数

> 原文:[https://www . geesforgeks . org/python-乘法-字典-值乘常数/](https://www.geeksforgeeks.org/python-multiply-dictionary-value-by-constant/)

有时候，在使用字典时，我们可能会遇到一个用例，在这个用例中，我们需要在字典中将特定键的值乘以 K。这看起来是一个非常直接的问题，但是当不知道某个键的存在时，catch 就会出现，因此有时会变成一个两步的过程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`get()`**
get 函数可以用 1 初始化一个不存在的键，然后产品就可以了。这样可以避免密钥不存在的问题。

```py
# Python3 code to demonstrate working of
# Multiply Dictionary Value by Constant
# Using get()

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'for' : 4, 'CS' : 5}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Initialize K 
K = 5

# Using get()
# Multiply Dictionary Value by Constant
test_dict['best'] = test_dict.get('best', 1) * K

# printing result 
print("Dictionary after the multiplication of key : " + str(test_dict))
```

**Output :**

```py
The original dictionary : {'for': 4, 'is': 2, 'CS': 5, 'gfg': 1}
Dictionary after the multiplication of key : {'for': 4, 'is': 2, 'CS': 5, 'best': 5, 'gfg': 1}

```