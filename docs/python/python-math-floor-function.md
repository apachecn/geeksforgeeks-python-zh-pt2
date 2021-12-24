# Python | math.floor()函数

> 原文:[https://www.geeksforgeeks.org/python-math-floor-function/](https://www.geeksforgeeks.org/python-math-floor-function/)

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。`**math.floor()**`函数返回不大于 x 的最大整数，如果数字已经是整数，则返回相同的数字。

```py
Syntax: math.floor(x)

Parameter:
x: This is a numeric expression.

Returns:  largest integer not greater than x.
```

**代码#1:**

```py
# Python code to demonstrate the working of floor()

# importing "math" for mathematical operations 
import math 

x = 33.7

# returning the floor of 33.7
print ("The floor of 33.7 is : ", end ="") 
print (math.floor(x))
```

**Output:**

```py
The floor of 33.7 is : 33

```

**代码#2:**

```py
# Python code to demonstrate the working of floor()

# importing "math" for mathematical operations 
import math 

# prints the floor using floor() method 
print ("math.floor(-13.1) : ", math.floor(-13.1))
print ("math.floor(101.96) : ", math.floor(101.96))
```

**Output:**

```py
math.floor(-13.1) :  -14
math.floor(101.96) :  101

```