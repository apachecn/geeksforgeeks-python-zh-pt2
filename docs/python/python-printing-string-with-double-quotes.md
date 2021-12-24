# Python |带双引号的打印字符串

> 原文:[https://www . geesforgeks . org/python-printing-string-带双引号/](https://www.geeksforgeeks.org/python-printing-string-with-double-quotes/)

很多时候，在使用 Python 字符串时，我们遇到一个问题，我们需要在字符串中使用双引号，然后希望打印它。这种问题出现在许多领域，如日常编程和网络开发领域。让我们讨论执行这项任务的某些方法。

**方法一:使用反斜杠(“\”)**
这是解决这个问题的一种方法。在这种情况下，我们只需在双引号前加一个反斜杠，它就会被转义。

```py
# Python3 code to demonstrate working of 
# Printing String with double quotes
# Using backslash

# initializing string
# using backslash
test_str = "geeks\"for\"geeks"

# printing string
print("The string escaped with backslash : " + test_str)
```

**Output :**

```py
The string escaped with backslash : geeks"for"geeks

```