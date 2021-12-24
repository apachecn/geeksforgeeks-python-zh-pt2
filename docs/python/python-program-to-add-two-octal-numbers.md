# Python 程序添加两个八进制数

> 原文:[https://www . geesforgeks . org/python-program-to-add-two-octal-numbers/](https://www.geeksforgeeks.org/python-program-to-add-two-octal-numbers/)

给定两个八进制数，任务是编写一个 Python 程序来计算它们的和。

**示例:**

```py
Input: a = "123", b = "456"
Output: 601

Input: a = "654", b = "321"
Output: 1175
```

**进场:**

要在 python 中添加两个八进制值，我们首先将它们转换为十进制值，然后添加它们，最后再次将它们转换为八进制值。要转换数字，我们将使用[**【oct()**](https://www.geeksforgeeks.org/python-oct-function/)功能。 *oct()* 函数是 Python3 中内置的方法之一。 *oct()* 方法获取一个整数，并以字符串格式返回其八进制表示。我们还将使用 [**int()**](https://www.geeksforgeeks.org/python-int-function/) 函数将数字转换为十进制形式。Python 和 Python3 中的 *int()* 函数将给定基数的数字转换为十进制。

**以下是基于以上解释的实现:**

**例 1:**

## 蟒蛇 3

```py
# Python program to add two hexadecimal numbers.

# Driver code
# Declaring the variables
a = "123"
b = "456"

# Calculating octal value using function
sum = oct(int(a, 8) + int(b, 8))

# Printing result
print(sum[2:])
```

**输出:**

```py
601
```

**例 2:**

## 蟒蛇 3

```py
# Python program to add two hexadecimal numbers.

# Driver code
# Declaring the variables
a = "654"
b = "321"

# Calculating octal value using function
sum = oct(int(a, 8) + int(b, 8))

# Printing result
print(sum[2:])
```

**输出:**

```py
1175
```