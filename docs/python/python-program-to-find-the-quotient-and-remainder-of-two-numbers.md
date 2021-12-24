# Python 程序求两个数的商和余数

> 原文:[https://www . geeksforgeeks . org/python-程序查找二进制数的商和余数/](https://www.geeksforgeeks.org/python-program-to-find-the-quotient-and-remainder-of-two-numbers/)

给定两个数 n 和 m，任务是用 n 除以 m，求出两个数的商和余数。

**示例:**

```py
Input:
n = 10
m = 3
Output:
Quotient:  3
Remainder 1

Input
n = 99
m = 5
Output:
Quotient:  19
Remainder 4

```

**方法 1:** 天真方法

最简单的方法是使用二重除法**(/)**运算符求商，使用模数 **(%)** 运算符求余数。

**示例:**

## 蟒蛇 3

```py
# Python program to find the
# quotient and remainder

def find(n, m):

    # for quotient
    q = n//m
    print("Quotient: ", q)

    # for remainder
    r = n%m
    print("Remainder", r)

# Driver Code
find(10, 3)
find(99, 5)
```

**输出:**

```py
Quotient:  3
Remainder 1
Quotient:  19
Remainder 4

```

**方法二:**采用 [divmod()](https://www.geeksforgeeks.org/divmod-python-application/) 方法

Divmod()方法将两个数字作为参数，并返回包含商和余数的元组。

**示例:**

## 蟒蛇 3

```py
# Python program to find the
# quotient and remainder using
# divmod() method

q, r = divmod(10, 3)
print("Quotient: ", q)
print("Remainder: ", r)

q, r = divmod(99, 5)
print("Quotient: ", q)
print("Remainder: ", r)
```

**输出:**

```py
Quotient:  3
Remainder 1
Quotient:  19
Remainder 4

```