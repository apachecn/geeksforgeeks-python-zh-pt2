# Python 程序将 int 转换为指数

> 原文:[https://www . geesforgeks . org/python-program-to-convert-int-to-index/](https://www.geeksforgeeks.org/python-program-to-convert-int-to-exponential/)

给定一些 int 类型，任务是编写一个 Python 程序将其转换为指数。

**例:**

```
Input: 19
Output: 1.900000e+01

Input: 2002
Output: 2.002000e+03

Input: 110102
Output: 1.101020e+05
```

**进场:**

*   我们将首先声明并初始化一个整数
*   然后我们将使用甲酸方法将数字从整数转换为指数类型。
*   然后我们将打印转换后的值。

**语法:**

```
String {field_name:conversion} Example.format(value)
```

**错误和异常:**

> 值错误:此方法中类型转换时出现错误。

更多的参数可以包含在我们语法的大括号中。使用格式代码语法 **{field_name: conversion}** ，其中 field_name 指定参数对 **str.format()方法**的索引号，转换是指数据类型的转换代码。

**例:**

## 蟒 3

```
# Python program to convert int to exponential

# Declaring the integer number
int_number = 110102

# Converting the integer number to exponential number
exp_number = "{:e}".format(int_number)

# Printing the converted number
print("Integer Number:",int_number)
print("Exponent Number:",exp_number)
```

**输出:**

```
Integer Number: 110102
Exponent Number: 1.101020e+05
```