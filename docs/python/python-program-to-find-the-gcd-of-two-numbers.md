# Python 程序查找两个数字的 gcd

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-gcd-of-two-numbers/](https://www.geeksforgeeks.org/python-program-to-find-the-gcd-of-two-numbers/)

给定两个数字。任务是找到这两个数字的 GCD。

**使用 STL :**

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。math.gcd()函数计算其参数中提到的 2 个数字的最大公约数。

> **语法:** math.gcd(x，y)
> 
> **参数:**
> 
> **x** :必须计算 gcd 的非负整数。
> 
> **y** :必须计算 gcd 的非负整数。
> 
> **计算给定参数 x 和 y 的 GCD 后返回:**一个绝对/正整数值。
> 
> **异常:**当 x 和 y 都为 0 时，函数返回 0，如果任何数字是字符，将引发类型错误。

## 蟒蛇 3

```py
# Python code to demonstrate the working of gcd()
# importing "math" for mathematical operations
import math

# prints 12
print("The gcd of 60 and 48 is : ", end="")
print(math.gcd(60, 48))
```

**Output**

```py
The gcd of 60 and 48 is : 12

```

**使用递归:**

## 蟒蛇 3

```py
# Python code to demonstrate naive
# method to compute gcd ( recursion )

def hcf(a, b):
    if(b == 0):
        return a
    else:
        return hcf(b, a % b)

a = 60
b = 48

# prints 12
print("The gcd of 60 and 48 is : ", end="")
print(hcf(60, 48))
```

**Output**

```py
The gcd of 60 and 48 is : 12

```

**使用欧几里德算法:**

欧几里德算法(或欧几里德算法)是一种有效寻找两个数的最大公约数(GCD)的方法。两个整数 X 和 Y 的 GCD 是除 X 和 Y 两者的最大数(不留余数)。

算法的伪代码-

1.  让 a，b 是两个数字
2.  a mod b = R
3.  设 a = b，b = R
4.  重复步骤 2 和 3，直到模 b 大于 0
5.  GCD = b
6.  结束

## 蟒蛇 3

```py
# Recursive function to return gcd of a and b
def gcd(a, b):

    # Everything divides 0
    if (a == 0):
        return b
    if (b == 0):
        return a

    # base case
    if (a == b):
        return a

    # a is greater
    if (a > b):
        return gcd(a-b, b)
    return gcd(a, b-a)

# Driver program to test above function
a = 98
b = 56
if(gcd(a, b)):
    print('GCD of', a, 'and', b, 'is', gcd(a, b))
else:
    print('not found')
```

**Output**

```py
GCD of 98 and 56 is 14

```