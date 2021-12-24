# 检查一个数字是正还是负还是零的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-check-number-是正还是负还是零/](https://www.geeksforgeeks.org/python-program-to-check-whether-a-number-is-positive-or-negative-or-zero/)

给定一个数字。任务是检查数字是正数、负数还是零。

**例:**

```py
Input: 5
Output: Positive

Input: -5
Output: Negative

```

**进场:**

我们将使用 Python 中的 [if-elif](https://www.geeksforgeeks.org/python-if-else/) 语句。我们将检查数字是大于零还是小于零或等于零。

下面是实现。

T2T4

```py
# Python program to check whether
# the number is positive, negative
# or equal to zero

def check(n):

    # if the number is positive
    if n > 0:
        print("Positive")

    # if the number is negative
    elif n < 0:
        print("Negative")

    # if the number is equal to
    # zero
    else:
        print("Equal to zero")

# Driver Code
check(5)
check(0)
check(-5)
```

T5

**输出:**

```py
Positive
Equal to zero
Negative

```