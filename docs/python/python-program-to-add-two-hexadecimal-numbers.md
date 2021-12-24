# Python 程序添加两个十六进制数

> 原文:[https://www . geesforgeks . org/python-program-to-add-two-十六进制数字/](https://www.geeksforgeeks.org/python-program-to-add-two-hexadecimal-numbers/)

给定两个十六进制数，编写一个 Python 程序来计算它们的和。

**示例:**

> **输入:** a = "01B "，b = "378"
> **输出:** 393
> **解释:**
> B(十进制 11)+8 = 19(十六进制 13)，因此加法位= 3，进位= 1
> 1 + 7 + 1(进位)= 9，因此加法位= 9，进位= 0
> 0 + 3 + 0(进位)= 3，因此加法位= 3，进位= 0
> 
> **输入:** a = "AD "，b = "1B"
> **输出:** C8
> **解释:**T8】D(12 月 13 日)+B(12 月 11 日)= 24(十六进制 18)，故加法位= 8，进位= 1
> A(12 月 10 日)+ 1 + 1(进位)= 12(十六进制 C)，加法位= C 进位= 0
> AD + 1B = C8

**进场:**

要在 python 中添加两个十六进制值，我们将首先将它们转换为十进制值，然后添加它们，最后再次将它们转换为十六进制值。要转换数字，我们将使用 [**十六进制()**](https://www.geeksforgeeks.org/python-hex-function/) 函数*十六进制(*)函数是 Python3 中的内置函数之一，用于将整数转换为相应的十六进制形式。我们还将使用 [**int()**](https://www.geeksforgeeks.org/python-int-function/) 函数将数字转换为十进制形式。Python 和 Python3 中的 *int()* 函数将给定基数的数字转换为十进制。

**以下是基于上述方法的实现:**

**例 1:**

## 蟒蛇 3

```py
# Python program to add two hexadecimal numbers.

# Driver code
# Declaring the variables
a = "01B"
b = "378"

# Calculating hexadecimal value using function
sum = hex(int(a, 16) + int(b, 16))

# Printing result
print(sum[2:])
```

**输出:**

```py
393
```

**例 2:**

## 蟒蛇 3

```py
# Python program to add two hexadecimal numbers.

# Driver code
# Declaring the variables
a = "B"
b = "C"

# Calculating hexadecimal value using function
sum = hex(int(a, 16) + int(b, 16))

# Printing result
print(sum[2:])
```

**输出:**

```py
17
```