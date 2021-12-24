# Python | math.gcd()函数

> 原文:[https://www.geeksforgeeks.org/python-math-gcd-function/](https://www.geeksforgeeks.org/python-math-gcd-function/)

在 Python 中，数学模块包含许多数学运算，使用该模块可以轻松执行这些运算。`**math.gcd()**`函数计算其自变量中提到的 2 个数的最大公约数。

> **语法:** math.gcd(x，y)
> 
> **参数:**
> **x :** 必须计算 gcd 的非负整数。
> **y :** 必须计算 gcd 的非负整数。
> 
> **计算给定参数 x 和 y 的 GCD 后返回:**一个绝对/正整数值。
> 
> **异常:**当 x 和 y 都为 0 时，函数返回 0，如果任何数字是字符，将引发类型错误。

**代码#1:**

```py
# Python code to demonstrate the working of gcd()

# importing "math" for mathematical operations 
import math 

# prints 12 
print ("The gcd of 60 and 48 is : ", end ="") 
print (math.gcd(60, 48)) 
```

**Output:**

```py
The gcd of 60 and 48 is : 12

```

**代码#2:**

```py
# Python code to demonstrate the working of gcd()

# importing "math" for mathematical operations 
import math 

# prints gcd of x, y
print ("math.gcd(44, 12) : ", math.gcd(44, 12))
print ("math.gcd(69, 23) : ", math.gcd(65, 45))
```

**Output:**

```py
math.gcd(44, 12) :  4
math.gcd(69, 23) :  5

```

**代码#3:** 解释异常。

```py
# Python code to demonstrate gcd() 
# method exceptions 
import math 

# prints 0 
print ("The gcd of 0 and 0 is : ", end ="") 
print (math.gcd(0, 0)) 

# Produces error 
print ("\nThe gcd of a and 13 is : ", end ="") 
print (math.gcd('a', 13)) 
```

**输出:**

```py
The gcd of 0 and 0 is : 0

The gcd of a and 13 is : 
TypeError: 'str' object cannot be interpreted as an integer
```