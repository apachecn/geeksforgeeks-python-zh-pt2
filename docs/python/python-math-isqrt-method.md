# Python | math.isqrt()方法

> 原文:[https://www.geeksforgeeks.org/python-math-isqrt-method/](https://www.geeksforgeeks.org/python-math-isqrt-method/)

**Python 中的数学模块**包含多个数学运算，使用该模块可以轻松执行。
**Python 中的 math.isqrt()** 方法用于获取给定非负整数值 n 的整数平方根，该方法返回 n 的精确平方根的 floor 值或等效的最大整数 a，使得 a <sup>2</sup> < = n。

**注意:**这个方法在 Python 版本中是新的。

> **语法:** math.isqrt(n)
> 
> **参数:**
> **n** :非负整数
> 
> **返回:**一个整数值，代表给定非负整数 n 的平方根的下限。

**代码#1:** 使用 math.isqrt()方法

## 蟒蛇 3

```py
# Python Program to explain
# math.isqrt() method

import math

n = 10

# Get the floor value of
# exact square root of n
sqrt = math.isqrt(n)
print(n)

n = 100

# Get the floor value of
# exact square root of n
sqrt = math.isqrt(n)
print(n)
```

**Output:** 

```py
3
10
```

**代码#2:** 使用 math.isqrt()方法检查给定的整数是否为完美平方。

## 蟒蛇 3

```py
# Python Program to explain
# math.isqrt() method

import math

def isPerfect(n):

    # Get the floor value of
    # exact square root of n
    sqrt = math.isqrt(n)

    if sqrt * sqrt == n:
        print(f"{n} is perfect square")

    else :
        print(f"{n} is not a perfect square")

# Driver's code
isPerfect(100)
isPerfect(10)
```

**Output:** 

```py
100 is perfect square
10 is not a perfect square
```

**代码#3:** 使用 math.isqrt()方法寻找 n 的下一个完美平方。

## 蟒蛇 3

```py
# Python Program to explain
# math.isqrt() method

import math

n = 11

def Next(n):

    # Get the ceiling of
    # exact square root of n
    ceil = 1 + math.isqrt(n)

    # print the next perfect square of n
    print("Next perfect square of {} is {}".
          format(n, ceil*ceil))

# Driver's code
Next(11)
Next(37)
```

**Output:** 

```py
Next perfect square after 11 is 16
Next perfect square after 37 is 49
```