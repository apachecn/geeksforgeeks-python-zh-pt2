# Python 数学函数| copysign()

> 原文:[https://www . geesforgeks . org/python-math-function-copy sign/](https://www.geeksforgeeks.org/python-math-function-copysign/)

math.copysign()是 Python 标准数学库中存在的一个函数。该函数返回一个浮点值，由参数 x 的幅度和参数 y 的符号(+ve 或-ve)组成。

> **语法:** math.copysign(x，y)
> 
> **参数:**
> x:需要转换的整数值
> y:需要符号的整数
> 
> **返回:**由参数 x 的幅度和参数 y 的符号组成的浮点值。

**代码#1:**

```
# Python code to demonstrate copy.sign() function
import math

def func():
    a = 5
    b = -7

    # implementation of copysign
    c = math.copysign(a, b)

    return c

print (func())
```

**输出:**

```
-5.0
```

**代码#2:**

```
# Python code to demonstrate copy.sign() function
import math

def func():
    a = 10
    b = 10

    # implementation of copysign
    c = math.copysign(a, b)

    return c

print (func())
```

**输出:**

```
10
```