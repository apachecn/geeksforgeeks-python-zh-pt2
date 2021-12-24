# Python–值长度字典

> 原文:[https://www . geesforgeks . org/python-value-length-dictionary/](https://www.geeksforgeeks.org/python-value-length-dictionary/)

有时候，在使用 Python 字典时，我们可能会遇到这样的问题，我们需要将字典的值映射到它的长度。这种应用可以出现在许多领域，包括网页开发和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `len()`**
这是可以执行此任务的方式之一。在这种情况下，我们提取字典的值，并用 len()计算的长度映射它。

```
# Python3 code to demonstrate working of 
# Value length dictionary
# Using loop + len()

# initializing dictionary
test_dict = {1 : 'gfg', 2 : 'is', 3 : 'best'}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Value length dictionary
# Using loop + len()
res = {}
for val in test_dict.values():
    res[val] = len(val)

# printing result 
print("The value-size mapped dictionary is : " + str(res)) 
```

**Output :**

```
The original dictionary is : {1: 'gfg', 2: 'is', 3: 'best'}
The value-size mapped dictionary is : {'is': 2, 'best': 4, 'gfg': 3}

```