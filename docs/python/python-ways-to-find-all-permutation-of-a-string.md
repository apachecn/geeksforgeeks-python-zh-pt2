# Python |查找字符串所有排列的方法

> 原文:[https://www . geesforgeks . org/python-查找字符串全排列的方法/](https://www.geeksforgeeks.org/python-ways-to-find-all-permutation-of-a-string/)

给定一个字符串，编写一个 Python 程序来找出字符串的所有可能排列。让我们讨论几个解决问题的方法。
**方法#1:使用天真法**

## 蟒蛇 3

```
# Python code to demonstrate
# to find all permutation of
# a given string

# Initialising string
ini_str = "abc"

# Printing initial string
print("Initial string", ini_str)

# Finding all permutation
result = []

def permute(data, i, length):
    if i == length:
        result.append(''.join(data) )
    else:
        for j in range(i, length):
            # swap
            data[i], data[j] = data[j], data[i]
            permute(data, i + 1, length)
            data[i], data[j] = data[j], data[i] 
permute(list(ini_str), 0, len(ini_str))

# Printing result
print("Resultant permutations", str(result))
```

**Output:** 

```
Initial string abc
Resultant permutations ['abc', 'acb', 'bac', 'bca', 'cba', 'cab']
```

**方法 2:使用迭代工具**

## 蟒蛇 3

```
# Python code to demonstrate
# to find all permutation of
# a given string

from itertools import permutations

# Initialising string
ini_str = "abc"

# Printing initial string
print("Initial string", ini_str)

# Finding all permutation
permutation = [''.join(p) for p in permutations(ini_str)]
# Printing result
print("Resultant List", str(permutation))
```

**Output:** 

```
Initial string abc
Resultant List ['abc', 'acb', 'bac', 'bca', 'cab', 'cba']
```