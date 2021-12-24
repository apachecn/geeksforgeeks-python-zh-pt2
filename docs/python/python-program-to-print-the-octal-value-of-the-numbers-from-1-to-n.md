# Python 程序打印从 1 到 N 的数字的八进制值

> 原文:[https://www . geesforgeks . org/python-program-to-print-the-octal-value-of-numbers-from-1-n/](https://www.geeksforgeeks.org/python-program-to-print-the-octal-value-of-the-numbers-from-1-to-n/)

给定一个数字 N，任务是编写一个 Python 程序来打印从 1 到 N 的数字的八进制值

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
        10
        11
        12
        13
```

**进场:**

*   我们将把 N 的值作为输入。
*   然后，我们将运行从 1 到 N+1 的 for 循环，并通过 [oct()](https://www.geeksforgeeks.org/python-oct-function/) 功能遍历每个“ **i** ”。
*   打印每个八进制值。

**注:**的 **oct()** 功能**T5】是 Python3 内置的方法之一。oct()方法接受一个整数，并以字符串格式返回其八进制表示形式。**

**以下是基于上述方法的实现:**

## python 3

```
# Python program to print the octal value of the
# numbers from 1 to N

# Function to find the octal value of the numbers
# in the range 1 to N
def octal_in_range(n):

    # For loop traversing from 1 to N (Both Inclusive)
    for i in range(1, n+1):

        # Printing octal value of i
        print(oct(i)[2:])

# Calling the function with input 3
print("Input: 3")
octal_in_range(3)

# Calling the function with input 11
print("Input: 11")
octal_in_range(11)
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
10
11
12
13
```