# 复数加减 Python 程序

> 原文:[https://www . geesforgeks . org/python-复数加减程序/](https://www.geeksforgeeks.org/python-program-for-addition-and-subtraction-of-complex-numbers/)

给定两个复数 z1 和 z2。任务是加减给定的复数。
**复数相加:**在 Python 中，可以使用+运算符相加复数。
**示例:**

```
Input:  2+3i, 4+5i
Output: Addition is : 6+8i

Input: 2+3i, 1+2i
Output: Addition is : 3+5i
```

**示例:**

## 蟒蛇 3

```
# Python program to add
# two complex numbers

# function that returns
# a complex number after
# adding
def addComplex( z1, z2):
    return z1 + z2

# Driver's code
z1 = complex(2, 3)
z2 = complex(1, 2)
print( "Addition is : ", addComplex(z1, z2))
```

**输出:**

```
Addition is :  (3+5j)
```

**复数减法:**Python 中的复数可以使用–运算符进行减法运算。
**例:**

```
Input: 2+3i, 4+5i
Output: Subtraction is : -2-2i

Input: 2+3i, 1+2i
Output: Subtraction is : 1+1i
```

**示例:**

## 蟒蛇 3

```
# Python program to subtract
# two complex numbers

# function that returns
# a complex number after
# subtracting
def subComplex( z1, z2):
    return z1-z2

# driver program
z1 = complex(2, 3)
z2 = complex(1, 2)
print( "Subtraction is : ", subComplex(z1, z2))
```

**输出:**

```
Subtraction is :  (1+1j)
```