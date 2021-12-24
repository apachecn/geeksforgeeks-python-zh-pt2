# Python 程序打印从 1 到 N 的十六进制数值

> 原文:[https://www . geesforgeks . org/python-program-to-print-十六进制-从 1 到 n 的数字值/](https://www.geeksforgeeks.org/python-program-to-print-the-hexadecimal-value-of-the-numbers-from-1-to-n/)

给定一个数字 N，任务是编写一个 Python 程序来打印从 1 到 N 的数字的十六进制值

**例:**

```
Input: 3
Output: 1
        2
        3

Input: 11
Output: 1
        2
        3
        4
        5
        6
        7
        8
        9
        a
        b
```

**进场:**

*   我们将把 N 的值作为输入。
*   然后，我们将运行从 1 到 N+1 的 for 循环，并通过 [hex()](https://www.geeksforgeeks.org/python-hex-function/) 函数遍历每个“ **i** ”。
*   打印每个十六进制值。

**注意:****hex()**函数是 Python3 中的内置函数之一，用于将一个整数转换为其对应的十六进制形式。

**以下是基于上述方法的实现:**

## python 3

```
# Python program to print the hexadecimal value of the 
# numbers from 1 to N

# Function to find the hexadecimal value of the numbers
# in the range 1 to N
def hex_in_range(n):

    # For loop traversing from 1 to N (Both Inclusive)
    for i in range(1, n+1):

        # Printing hexadecimal value of i
        print(hex(i)[2:])

# Calling the function with input 3
print("Input: 3")
hex_in_range(3)

# Calling the function with input 11
print("Input: 11")
hex_in_range(11)
```

**输出:**

```
Input: 3
1
2
3
Input: 11
1
2
3
4
5
6
7
8
9
a
b
```