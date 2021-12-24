# Python |将字典键解包成元组

> 原文:[https://www . geesforgeks . org/python-解包-字典-密钥-转换为元组/](https://www.geeksforgeeks.org/python-unpacking-dictionary-keys-into-tuple/)

在某些情况下，我们可能会遇到这样的问题:我们需要将字典键解包到元组中。这种问题可能发生在我们只关心字典的关键字并希望有一个元组的情况下。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple()`**

将字典转换成元组的简单类型实际上完成了所需的任务。这个函数只接受关键字，并根据需要将它们转换成关键字元组。

```py
# Python3 code to demonstrate working of
# Unpacking dictionary keys into tuple
# Using tuple()

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using tuple()
# Unpacking dictionary keys into tuple
res = tuple(test_dict)

# printing result
print("The unpacked dict. keys into tuple is :  " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 3, 'is': 2, 'Gfg': 1}
The unpacked dict. keys into tuple is :  ('best', 'is', 'Gfg')

```

**方法 2:使用`"=" operator`和多个变量**
该方法也可用于执行该特定任务。在这种情况下，我们将逗号分隔的变量分配给字典。我们在字典中使用的变量和关键字一样多。在密钥未知或数量较多的情况下，不建议使用此方法。

```py
# Python3 code to demonstrate working of
# Unpacking dictionary keys into tuple
# Using "=" operator and multiple variables

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using "=" operator and multiple variables
# Unpacking dictionary keys into tuple
a, b, c = test_dict
res = a, b, c

# printing result
print("The unpacked dict. keys into tuple is :  " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 3, 'is': 2, 'Gfg': 1}
The unpacked dict. keys into tuple is :  ('best', 'is', 'Gfg')

```