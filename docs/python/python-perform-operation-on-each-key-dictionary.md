# Python |对各键字典进行操作

> 原文:[https://www . geesforgeks . org/python-每键执行操作-字典/](https://www.geeksforgeeks.org/python-perform-operation-on-each-key-dictionary/)

有时候，在使用字典时，我们可能会遇到一个问题，我们需要对每个键值执行特定的操作。这类问题可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行这个任务的天真方法。在这种情况下，我们只需运行一个循环来遍历字典中的每个键，并执行所需的操作。

```py
# Python3 code to demonstrate working of
# Perform operation on each key dictionary
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 6, 'is' : 4, 'best' : 7}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using loop
# Perform operation on each key dictionary
for key in test_dict:    
    test_dict[key] *= 3

# printing result 
print("The dictionary after triple each key's value : " + str(test_dict))
```

**Output :**

> 原始字典:{'is': 4，' gfg': 6，' best': 7}
> 将每个键的值加三倍后的字典:{'is': 12，' gfg': 18，' best': 21}