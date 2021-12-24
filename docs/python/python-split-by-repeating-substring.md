# Python |重复子串拆分

> 原文:[https://www . geesforgeks . org/python-按重复子串拆分/](https://www.geeksforgeeks.org/python-split-by-repeating-substring/)

有时，在使用 Python 字符串时，我们可能会遇到需要执行拆分的问题。这可以是习惯性的。在这种情况下，我们可以有一个分裂，我们需要分裂所有的重复。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用*运算符+ len()**
这是我们可以执行此任务的方式之一。在这种情况下，我们计算重复字符串的长度，然后划分列表以获得根，并使用*运算符构建新的列表。

```py
# Python3 code to demonstrate working of 
# Split by repeating substring
# Using * operator + len()

# initializing string
test_str = "gfggfggfggfggfggfggfggfg"

# printing original string
print("The original string is : " + test_str)

# initializing target
K = 'gfg'

# Split by repeating substring
# Using * operator + len()
temp = len(test_str) // len(str(K))
res = [K] * temp

# printing result 
print("The split string is : " + str(res)) 
```

**Output :**

```py
The original string is : gfggfggfggfggfggfggfggfg
The split string is : ['gfg', 'gfg', 'gfg', 'gfg', 'gfg', 'gfg', 'gfg', 'gfg']

```