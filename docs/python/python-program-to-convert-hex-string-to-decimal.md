# Python 程序将十六进制字符串转换为十进制

> 原文:[https://www . geesforgeks . org/python-program-convert-hex-string-to-decimal/](https://www.geeksforgeeks.org/python-program-to-convert-hex-string-to-decimal/)

在 Python 中，元素转换是一个非常有用的工具，因为它提供的方式比其他语言简单得多。这使得 Python 成为一种健壮的语言，因此对于程序员来说，相互转换的知识总是一个优势。本文讨论十六进制字符串到十进制数的转换。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`int()`**

这个函数可以用来执行这个特殊的任务，添加一个参数(16)这个函数可以将十六进制的字符串数字转换为十六进制，同时将其转换为整数。

```py
# Python3 code to demonstrate
# converting hexadecimal string to decimal
# Using int()

# initializing string 
test_string = 'A'

# printing original string 
print("The original string : " + str(test_string))

# using int()
# converting hexadecimal string to decimal
res = int(test_string, 16)

# print result
print("The decimal number of hexadecimal string : " + str(res))
```

**Output :**

```py
The original string : A
The decimal number of hexadecimal string : 10

```

**方法 2:使用`ast.literal_eval()`**

我们可以通过使用预测基数并将数字字符串转换为十进制数字格式的文字求值函数来执行这个特定的函数。

```py
# Python3 code to demonstrate
# converting hexadecimal string to decimal
# Using ast.literal_eval()
from ast import literal_eval

# initializing string 
test_string = '0xA'

# printing original string 
print("The original string : " + str(test_string))

# using ast.literal_eval()
# converting hexadecimal string to decimal
res = literal_eval(test_string)

# print result
print("The decimal number of hexadecimal string : " + str(res))
```

**Output :**

```py
The original string : A
The decimal number of hexadecimal string : 10

```