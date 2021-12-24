# Python 数学函数| hypt()

> 原文:[https://www.geeksforgeeks.org/python-math-function-hypot/](https://www.geeksforgeeks.org/python-math-function-hypot/)

***【海波】(*** )函数是 Python 中的一个内置数学函数，它返回欧几里德范数，![ \sqrt{(x*x + y*y)} ](img/e05e95ebfcfac71d28d4268b22ed6470.png "Rendered by QuickLaTeX.com")。

**语法:**

```
hypot(x, y) 
```

**参数:**

```
x and y are numerical values 
```

**返回:**

```
Returns a float value having Euclidean norm, sqrt(x*x + y*y). 
```

**错误:**

```
When more then two arguments are 
passed, it returns a <font color="red">TypeError</font>.
```

**注意:**使用**海波()**功能前必须导入数学模块。

下面是*海波()*功能的演示:

**代码#1 :**

```
# Python3 program for hypot() function 

# Import the math module
import math

# Use of hypot function
print("hypot(3, 4) : ", math.hypot(3, 4))

# Neglects the negative sign
print("hypot(-3, 4) : ", math.hypot(-3, 4))

print("hypot(6, 6) : ", math.hypot(6, 6))
```

**输出:**

```
hypot(3, 4) :  5.0
hypot(-3, 4) :  5.0
hypot(6, 6) :  8.48528137423857

```

**代码#2 :**

```
# Python3 program for error in hypot() function 

# import the math module
import math

# Use of hypot() function
print("hypot(3, 4, 6) : ",  math.hypot(3, 4, 6))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/d8c8612ee97dd2c763e2836de644fac1.py", line 7, in 
    print("hypot(3, 4, 6) : ",  math.hypot(3, 4, 6))
TypeError: hypot expected 2 arguments, got 3

```

**实际应用:**
给定直角三角形的垂线和底边，求斜边。

使用勾股定理，该定理指出斜边(与直角相对的一边)的平方等于其他两边的平方之和。

因此，

```
 Hypotenuse = sqrt(p^2 + b^2) 
```

**代码#3 :**

```
# Python3 program for finding Hypotenuse
# in hypot() function 

# import the math module
from math import hypot

# Perpendicular and base
p = 3
b = 4

# Calculates the hypotenuse
print("Hypotenuse is:", hypot(p, b))
```

**输出:**

```
Hypotenuse is: 5.0

```