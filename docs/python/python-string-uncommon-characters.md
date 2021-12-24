# Python–字符串不常见字符

> 原文:[https://www . geeksforgeeks . org/python-string-un 不凡-characters/](https://www.geeksforgeeks.org/python-string-uncommon-characters/)

字符串操作之一可以是计算两个字符串的不常见字符，即输出出现在两个字符串中的不常见值。本文通过不同的方式处理相同的计算。

**方法一:使用 python 中的`set() + symmetric_difference()`**
Set 通常可以执行执行集合对称差等集合运算的任务。这个工具集也可以用来执行这个任务。首先，使用 set()将两个字符串转换为集合，然后使用 symmetric_difference()执行对称差分。返回排序后的集合。

```py
# Python 3 code to demonstrate 
# String uncommon characters
# using set() + symmetric_difference()

# initializing strings
test_str1 = 'GeeksforGeeks'
test_str2 = 'Codefreaks'

# Printing initial strings
print ("The original string 1 is : " + test_str1)
print ("The original string 2 is : " + test_str2)

# String uncommon characters
# using set() + symmetric_difference()
res = set(test_str1).symmetric_difference(test_str2)

# printing symmetric_difference
print ("The string uncommon elements are : " + str(res))
```

**Output :**

```py
The original string 1 is : GeeksforGeeks
The original string 2 is : Codefreaks
The string uncommon elements are : {'C', 'd', 'a', 'G'}

```