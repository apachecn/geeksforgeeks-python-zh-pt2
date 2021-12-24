# Python | math.fabs()函数

> 原文:[https://www.geeksforgeeks.org/python-math-fabs-function/](https://www.geeksforgeeks.org/python-math-fabs-function/)

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。`**math.fabs()**`函数返回数字的绝对值。

```
Syntax: math.fabs(x)

Parameter:
x: This is a numeric expression.

Returns: the absolute value of the number.
```

**代码#1:**

```
# Python code to demonstrate the working of fabs()

# importing "math" for mathematical operations 
import math 

x = -33.7

# returning the fabs of 33.7
print ("The fabs of 33.7 is : ", end ="") 
print (math.fabs(x))
```

**Output:**

```
The fabs of 33.7 is : 33.7

```

**代码#2:**

```
# Python code to demonstrate the working of fabs()

# importing "math" for mathematical operations 
import math 

# prints the fabs using fabs() method 
print ("math.fabs(-13.1) : ", math.fabs(-13.1))
print ("math.fabs(101.96) : ", math.fabs(101.96))
```

**Output:**

```
math.fabs(-13.1) :  13.1
math.fabs(101.96) :  101.96

```