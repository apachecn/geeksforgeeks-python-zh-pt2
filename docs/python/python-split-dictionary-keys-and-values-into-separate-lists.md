# Python |将字典键和值拆分成单独的列表

> 原文:[https://www . geesforgeks . org/python-split-dictionary-key-values-in-separate-list/](https://www.geeksforgeeks.org/python-split-dictionary-keys-and-values-into-separate-lists/)

给定一个字典，任务是将该字典分解成键，并将值分解成不同的列表。让我们讨论一下不同的方法。

**方法一:使用`built-in functions`**

```py
# Python code to demonstrate
# to split dictionary
# into keys and values

# initialising _dictionary
ini_dict = {'a' : 'akshat', 'b' : 'bhuvan', 'c': 'chandan'}

# printing iniial_dictionary
print("intial_dictionary", str(ini_dict))

# split dictionary into keys and values
keys = ini_dict.keys()
values = ini_dict.values()

# printing keys and values separately
print ("keys : ", str(keys))
print ("values : ", str(values))
```

**输出:**

```py
intial_dictionary {'a': 'akshat', 'b': 'bhuvan', 'c': 'chandan'}
keys :  dict_keys(['a', 'b', 'c'])
values :  dict_values(['akshat', 'bhuvan', 'chandan'])

```