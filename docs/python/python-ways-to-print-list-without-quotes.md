# Python |无引号列表打印方式

> 原文:[https://www . geesforgeks . org/python-打印方式-不带引号的列表/](https://www.geeksforgeeks.org/python-ways-to-print-list-without-quotes/)

每当我们在 Python 中打印列表时，我们通常会使用 str(list)，因为我们在输出列表中有单引号。假设问题要求打印没有引号的解决方案。让我们看看打印不带引号的列表的一些方法。

**方法一:使用`map()`**

```py
# Python code to demonstrate 
# printing list in a proper way

# Initialising list
ini_list = ['a', 'b', 'c', 'd']

# Printing initial list with str
print ("List with str", str(ini_list))

# Printing list using map
print ("List in proper method", '[%s]' % ', '.join(map(str, ini_list)))
```

**输出:**

```py
List with str ['a', 'b', 'c', 'd']
List in proper method [a, b, c, d]

```