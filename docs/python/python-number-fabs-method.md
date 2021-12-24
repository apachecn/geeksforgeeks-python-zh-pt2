# Python 数学库的 fabs()方法

> 原文:[https://www.geeksforgeeks.org/python-number-fabs-method/](https://www.geeksforgeeks.org/python-number-fabs-method/)

fabs()是 Python 2 和 Python 3 中数学库中指定的方法。

有时，在计算两个数字之间的差值以计算一个数字与另一个数字的接近度时，我们需要找到某个数字的大小，fabs()在处理 int 时会很方便，并且希望浮点数的结果进一步执行浮点比较，因为 fabs()将其每个大小都转换为浮点值。

> 语法:**晶圆厂(x)**
> 
> **参数:**
> **x :** 必须计算其大小的数。
> 
> **返回:**返回函数中传递的元素的大小。无论参数号的数据类型如何，始终返回一个浮点数。

**代码#1 :** 代码演示晶圆厂()工作

```py
# Python3 code to demonstrate 
# the working of fabs()

# for fabs()
import math

# initializing integer 
x = -2

# initializing float
y = -2.00

# printing magnitude and type of output
# type conversion to float
print("The magnitude of integer is : ", end ="")
print(math.fabs(x))
print("The type of output is : ", end ="")
print(type(math.fabs(x)))

print("\r")

# printing magnitude and type of output
print("The magnitude of float is : ", end ="")
print(math.fabs(y))
print("The type of output is : ", end ="")
print(type(math.fabs(y)))
```

输出:

```py
The magnitude of integer is : 2.0
The type of output is : 

The magnitude of float is : 2.0
The type of output is : 

```

**异常:**
这个方法有很多异常，因为它总是返回一个浮点数，所以当 python 无法将参数转换为浮点数时，这个函数会抛出一个异常。例如在字符串和复数的情况下。

**代码#2 :** 代码演示晶圆厂的异常()

```py
# Python3 code to demonstrate 
# the exception of fabs()

# for fabs()
import math

# initializing string
c = "gfg"

# initializing complex number
d = 4 + 2j

# checking for exceptions
try :
    print("The absolute value of string is :")
    print(math.fabs(c))

except Exception as e:
        print("Error !! The error on passing string is :")
        print(str(e))

print("\r")

try :
    print("The absolute value of complex is :")
    print(math.fabs(d))

except Exception as e:
        print("Error !! The error on passing complex is :")
        print(str(e))
```

输出:

```py
The absolute value of string is :
Error !! The error on passing string is :
a float is required

The absolute value of complex is :
Error !! The error on passing complex is :
can't convert complex to float

```