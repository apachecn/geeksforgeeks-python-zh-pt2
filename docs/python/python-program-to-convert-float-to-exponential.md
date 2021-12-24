# Python 程序将浮点转换为指数

> 原文:[https://www . geesforgeks . org/python-程序到转换-浮点到指数/](https://www.geeksforgeeks.org/python-program-to-convert-float-to-exponential/)

给定一个浮点数，任务是编写一个 Python 程序，将浮点数转换为指数。

**示例:**

```
Input: 19.0
Output: 1.900000e+01

Input: 200.2
Output: 2.002000e+02

Input: 1101.02
Output: 1.101020e+03
```

**进场:**

*   我们将首先声明并初始化一个浮点数。
*   然后我们将使用 format 方法将数字从整数转换为指数类型。
*   然后我们将打印转换后的值。

**语法:**

> 字符串{字段名称:转换}示例.格式(值)

**错误和异常:**

> 值错误:在此方法的类型转换过程中出现错误。

更多的参数可以包含在我们语法的大括号中。使用格式代码语法 **{field_name: conversion}** ，其中 field_name 指定参数对 **str.format()方法**的索引号，转换是指数据类型的转换代码。

**示例:**

## 蟒蛇 3

```
# Python program to convert float to exponential

# Declaring the float number
float_number = 1101.02

# Converting the float number to exponential number
exp_number = "{:e}".format(float_number)

# Printing the converted number
print("Float Number:",float_number)
print("Exponent Number:",exp_number)
```

**输出:**

```
Float Number: 1101.02
Exponent Number: 1.101020e+03
```