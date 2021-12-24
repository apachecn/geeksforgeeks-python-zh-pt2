# Python–求解多变量线性方程

> 原文:[https://www . geesforgeks . org/python-求解多元线性方程/](https://www.geeksforgeeks.org/python-solve-the-linear-equation-of-multiple-variable/)

**先决条件:** [症状解决()](https://www.geeksforgeeks.org/python-sympy-solve-method/)

在这篇文章中，我们将讨论如何解决一个多变量的线性方程。例如，假设方程中有两个变量。方程式如下:

> x+y =1
> 
> x-y =1

当我们解这个方程时，我们得到 x=1，y=0 作为解之一。在 Python 中，我们使用 Eq()方法从表达式创建一个方程。

> **语法:** Eq(表达式，RHS 值)

例如，如果我们有 x+y = 1 的表达式。它可以写成等式(x+y，1)

### 求解双变量方程

使用等式()方法构造方程。要求解这些方程，请将它们作为参数传递给 **solve()** 函数。

**示例:**

## 蟒蛇 3

```
# importing library sympy
from sympy import symbols, Eq, solve

# defining symbols used in equations
# or unknown variables
x, y = symbols('x,y')

# defining equations
eq1 = Eq((x+y), 1)
print("Equation 1:")
print(eq1)
eq2 = Eq((x-y), 1)
print("Equation 2")
print(eq2)

# solving the equation
print("Values of 2 unknown variable are as follows:")

print(solve((eq1, eq2), (x, y)))
```

**输出:**

```
Equation 1:
Eq(x + y, 1)
Equation 2
Eq(x - y, 1)
Values of 2 unknown variable are as follows:
{x: 1, y: 0} 

```

### 求解三变量方程

使用等式()构造以下等式，然后求解以找到未知变量。

> x +y+z =1
> 
> x+y+2z=1

**示例:**

## 蟒蛇 3

```
# importing library sympy
from sympy import symbols, Eq, solve

# defining symbols used in equations
# or unknown variables
x, y, z = symbols('x,y,z')

# defining equations
eq1 = Eq((x+y+z), 1)
print("Equation 1:")
print(eq1)

eq2 = Eq((x-y+2*z), 1)
print("Equation 2")
print(eq2)

eq3 = Eq((2*x-y+2*z), 1)
print("Equation 3")

# solving the equation and printing the 
# value of unknown variables
print("Values of 3 unknown variable are as follows:")
print(solve((eq1, eq2, eq3), (x, y, z)))
```

**输出:**

```
Equation 1:
Eq(x + y + z, 1)
Equation 2
Eq(x - y + 2*z, 1)
Equation 3
Values of 3 unknown variable are as follows:
{x: 0, y: 1/3, z: 2/3}
```