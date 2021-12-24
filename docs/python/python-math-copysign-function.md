# Python | math.copysign()函数

> 原文:[https://www . geesforgeks . org/python-math-copy sign-function/](https://www.geeksforgeeks.org/python-math-copysign-function/)

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。`**math.copysign(a, b)**`函数返回一个数值(绝对值)为 a 但符号为 b 的浮点数。

```py
Syntax: math.copysign(a, b)

Parameter:
a, b: numeric values.

Returns:  Return absolute value of *a* but the sign of *b*.
```

**代码#1:**

```py
# Python code to demonstrate the working of copysign()

# importing "math" for mathematical operations 
import math 

a = 5.2
b = -25

# returning the copysign 
print ("The copysign of 5.2 and -25 is : ", end ="") 
print (math.copysign(a, b))
```

**输出:**

```py
The copysign of 5.2 and -25 is : -5.2

```

**代码#2:**

```py
# Python code to demonstrate the working of factorial()

# importing "math" for mathematical operations 
import math 

# returning the copysign
print (math.copysign(-13, 25.5))
print (math.copysign(2.87, -15))
```

**输出:**

```py
13.0
-2.87

```