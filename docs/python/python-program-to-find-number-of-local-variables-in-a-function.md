# Python 程序查找函数中局部变量的个数

> 原文:[https://www . geesforgeks . org/python-program-to-find-number-of-local-variables-in-a-function/](https://www.geeksforgeeks.org/python-program-to-find-number-of-local-variables-in-a-function/)

给定一个 Python 程序，任务是找出函数中存在的局部变量的数量。

**示例:**

```
Input : a = 1
        b = 2.1
        str = 'GeeksForGeeks'

Output : 3

```

我们可以使用`co_nlocals()`函数，该函数返回函数使用的局部变量的数量，以获得期望的结果。

**代码#1:**

```
# Implementation of above approach

# A function containing 3 variables 
def fun():
    a = 1
    str = 'GeeksForGeeks'

# Driver program
print(fun.__code__.co_nlocals)
```

**Output:**

```
2

```

**代码#2:**

```
# Python program to find number of
# local variables in a function

# A function containing no variables 
def geek():
    pass

# A function containing 3 variables 
def fun():
    a, b, c = 1, 2.25, 333
    str = 'GeeksForGeeks'

# Driver program
print(geek.__code__.co_nlocals)
print(fun.__code__.co_nlocals)
```

**Output:**

```
0
4

```