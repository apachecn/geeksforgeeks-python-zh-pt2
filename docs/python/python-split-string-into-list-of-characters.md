# Python |将字符串拆分成字符列表

> 原文:[https://www . geesforgeks . org/python-拆分字符串成字符列表/](https://www.geeksforgeeks.org/python-split-string-into-list-of-characters/)

给定一个字符串，编写一个 Python 程序，将给定字符串的字符拆分成一个列表。

**示例:**

```py
Input : geeks
Output : ['g', 'e', 'e', 'k', 's']

Input : Word
Output : ['W', 'o', 'r', 'd']
```

**代码#1 :** 使用列表理解
这种方法使用列表理解将每个字符转换为列表。使用以下语法，您可以将字符串的字符拆分成一个列表。

## 蟒蛇 3

```py
# Python3 program to Split string into characters
def split(word):
    return [char for char in word]

# Driver code
word = 'geeks'
print(split(word))
```

**Output:** 

```py
['g', 'e', 'e', 'k', 's']
```

**代码#2 :** 向列表进行类型转换
Python 提供了使用列表()将字符串直接类型转换为列表的功能。

## 蟒蛇 3

```py
# Python3 program to Split string into characters
def split(word):
    return list(word)

# Driver code
word = 'geeks'
print(split(word))
```

**Output:** 

```py
['g', 'e', 'e', 'k', 's']
```