# Python 数学函数| modf()

> 原文:[https://www.geeksforgeeks.org/python-modf-function/](https://www.geeksforgeeks.org/python-modf-function/)

**modf()** 函数是 Python 中的一个内置函数，它返回两项元组中数字的小数和整数部分。两个部分都有和数字相同的符号。整数部分作为浮点数返回。

**语法:**

```py
modf(number) 
```

**参数:**

```py
There is only one mandatory parameter which is the number. 
```

**返回:**
这个方法返回一个两项元组中数字的小数和整数部分。两个部分都有和数字相同的符号。整数部分作为浮点数返回。

例外:

```py
TypeError:  If anything other then a float number is passed, it returns a type error. 
```

下面是 Python3 实现 ***modf()*** 的方法:

**代码#1**

```py
# Python3 program to demonstrate the function modf()

# This will import math module
import math   

# modf() function used with a positive number
print("math.modf(100.12) : ", math.modf(100.12))

# modf() function used with a negative number
print("math.modf(-100.72) : ", math.modf(-100.72)) 

print("math.modf(2) : ", math.modf(2)) 
```

**输出:**

```py
math.modf(100.12) :  (0.12000000000000455, 100.0)
math.modf(-100.72) :  (-0.7199999999999989, -100.0)
math.modf(2) :  (0.0, 2.0)

```

**代码#2 : <font color="red">类型错误</font>T3】**

```py
# Python3 program to demonstrate the  
# error in function modf()

# This will import math module
import math   

# modf() function used with a positive number
print("math.modf(100.12) : ", math.modf("100.12"))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/fa6d7643de17bafe9a0e0693458e4bdb.py", line 9, in 
    print("math.modf(100.12) : ", math.modf("100.12"))
TypeError: a float is required

```

**代码#3** :

```py
# Python3 program to demonstrate the 
# error in function modf()

# This will import math module
from math import modf

lst = [3.12, -5.14, 13.25, -5.21]
tpl = (33.12, -15.25, 3.15, -31.2)

# modf() function on elements of list
print("modf() on First list element : ", modf(lst[0]))
print("modf() on third list element : ", modf(lst[2]))

# modf() function on elements of tuple
print("modf() on Second tuple element : ", modf(tpl[1]))
print("modf() on Fourth tuple element : ", modf(tpl[3]))
```

输出:

```py
modf() on First list element :  (0.1200000000000001, 3.0)
modf() on third list element :  (0.25, 13.0)
modf() on Second tuple element :  (-0.25, -15.0)
modf() on Fourth tuple element :  (-0.1999999999999993, -31.0)

```

**实际应用:**
给定两个浮点数，将小数部分相乘，返回答案。

**代码#4 :**

```py
# Python3 program to demonstrate the 
# application of function modf()

# This will import math module
import math   

# modf() function to multiply fractional part 
a = math.modf(11.2) 
b = math.modf(12.3)

# Multiply the fractional part as is stored  
# in 0th index of both the tuple
print(a[0]*b[0])
```

输出:

```py
0.05999999999999993

```