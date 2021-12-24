# Python 程序打印帕斯卡三角形

> 原文:[https://www . geesforgeks . org/python-程序到打印-帕斯卡-三角形/](https://www.geeksforgeeks.org/python-program-to-print-pascals-triangle/)

帕斯卡三角形是基于 *nCr* 的三角形的图案，下图是帕斯卡三角形的图示。

**例:**

```
Input: N = 5
Output:
      1
     1 1
    1 2 1
   1 3 3 1
  1 4 6 4 1
```

**方法 1:** 使用 *nCr* 公式即 n！/(n-r)！r！

使用 nCr 公式后，图示变为:

```
          0C0
       1C0   1C1
    2C0   2C1   2C2
 3C0   3C1   3C2    3C3
```

**算法:**

*   Take the number of lines to print, assuming n.
*   Perform outer iteration I from 0 to n times to print lines.
*   Iterate internally for j from 0 to (n–1).
*   Print a single space "".
*   Close the inner ring (J-ring)//It needs left spacing.
*   Iterate internally for j from 0 to i.
*   Print [T0】 nCr 【T1] of I and J.
*   Close the inner ring.
*   Print line breaks after each internal iteration (\n).

**实现:**

## 蟒 3

```
# Print Pascal's Triangle in Python
from math import factorial

# input n
n = 5
for i in range(n):
    for j in range(n-i+1):

        # for left spacing
        print(end=" ")

    for j in range(i+1):

        # nCr = n!/((n-r)!*r!)
        print(factorial(i)//(factorial(j)*factorial(i-j)), end=" ")

    # for new line
    print()
```

**输出:**

```
      1
     1 1
    1 2 1
   1 3 3 1
  1 4 6 4 1
```

**时间复杂度:** O(N <sup>2</sup> )

**方法 2:** 我们可以通过以下二项式系数的概念来优化上述代码，行号*行*中的第 I 个条目是二项式系数 *C(行，i)* ，所有行都以值 1 开始。思路是用 *C(线，i-1)* 计算 *C(线，i)* 。

```
C(line, i) = C(line, i-1) * (line - i + 1) / i
```

**实现:**

## 蟒 3

```
# Print Pascal's Triangle in Python

# input n
n = 5

for i in range(1, n+1):
    for j in range(0, n-i+1):
        print(' ', end='')

    # first element is always 1
    C = 1
    for j in range(1, i+1):

        # first value in a line is always 1
        print(' ', C, sep='', end='')

        # using Binomial Coefficient
        C = C * (i - j) // j
    print()
```

**输出:**

```
      1
     1 1
    1 2 1
   1 3 3 1
  1 4 6 4 1
```

**时间复杂度:** O(N <sup>2</sup> )

**方法 3:** 这是打印帕斯卡三角形最优化的方法，这种方法基于 11 的幂。

```
11**0 = 1
11**1 = 11
11**2 = 121
11**3 = 1331
```

**实现:**

## 蟒 3

```
# Print Pascal's Triangle in Python

# input n
n = 5

# iterarte upto n
for i in range(n):
    # adjust space
    print(' '*(n-i), end='')

    # compute power of 11
    print(' '.join(map(str, str(11**i))))
```

**输出:**

```
      1
     1 1
    1 2 1
   1 3 3 1
  1 4 6 4 1
```

**时间复杂度:** O(N)

然而，这种方法仅适用于 n=5 的情况。