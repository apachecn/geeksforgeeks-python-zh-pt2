# Python | math.ceil()函数

> 原文:[https://www.geeksforgeeks.org/python-math-ceil-function/](https://www.geeksforgeeks.org/python-math-ceil-function/)

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。`**math.ceil()**`函数返回大于该数的最小整数值。如果数字已经是整数，则返回相同的数字。

```
Syntax: math.ceil(x)

Parameter:
x: This is a numeric expression.

Returns:  Smallest integer not less than x.
```

**代码#1:**

```
# Python code to demonstrate the working of ceil()

# importing "math" for mathematical operations 
import math 

x = 33.7

# returning the ceil of 33.7
print ("The ceil of 33.7 is : ", end ="") 
print (math.ceil(x))
```

**Output:**

```
The ceil of 33.7 is : 34

```

**代码#2:**

```
# Python code to demonstrate the working of ceil()

# importing "math" for mathematical operations 
import math 

# prints the ceil using ceil() method 
print ("math.ceil(-13.1) : ", math.ceil(-13.1))
print ("math.ceil(101.96) : ", math.ceil(101.96))
```

**Output:**

```
math.ceil(-13.1) :  -13
math.ceil(101.96) :  102

```