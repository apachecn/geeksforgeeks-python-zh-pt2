# Python–变量操作字典更新

> 原文:[https://www . geesforgeks . org/python-变量-操作-字典-更新/](https://www.geeksforgeeks.org/python-variable-operations-dictionary-update/)

有时，在使用 Python 字典时，我们可能会遇到这样一个问题，即我们需要在字典值之间执行某种操作后，使用分配的变量来填充字典值。这可以在日常编程中应用。让我们讨论执行这项任务的某些方法。
**方法#1:使用 lambda +字典理解**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用字典理解执行分配，使用 lambda 函数执行值计算。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Variable Operations Dictionary update
# Using lambda + dictionary comprehension

# helper functions
helper_fnc = {'Gfg': lambda: x + y,
         'best': lambda: x * y}

# initializing variables
x = 6
y = 7

# Variable Operations Dictionary update
# Using lambda + dictionary comprehension
res = {key: val() for key, val in hlper_fnc.items()}

# printing result
print("The Initialized dictionary : " + str(res))
```

**Output : **

```
The Initialized dictionary : {'best': 42, 'Gfg': 13}
```

**方法 2:使用操作员库**
该任务也可以使用上述功能执行。在这种情况下，我们使用操作员库提供的内置操作来完成这项任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Variable Operations Dictionary update
# Using lambda + dictionary comprehension
from operator import add, mul

# helper functions
helper_fnc = {'Gfg': add,
         'best': mul}

# initializing variables
x = 6
y = 7

# Variable Operations Dictionary update
# Using lambda + dictionary comprehension
res = {'Gfg' : hlper_fnc['Gfg'](x, y), 'best' : hlper_fnc['best'](x, y)}

# printing result
print("The Initialized dictionary : " + str(res))
```

**Output : **

```
The Initialized dictionary : {'best': 42, 'Gfg': 13}
```