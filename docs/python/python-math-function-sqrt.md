# Python 数学函数| sqrt()

> 原文:[https://www.geeksforgeeks.org/python-math-function-sqrt/](https://www.geeksforgeeks.org/python-math-function-sqrt/)

**sqrt()** 函数是 Python 编程语言中的一个内置函数，可以返回任意数字的平方根。

```
Syntax:
math.sqrt(x)

Parameter: 
x is any number such that x>=0 

Returns:
It returns the square root of the number 
passed in the parameter. 
```

```
# Python3 program to demonstrate the 
# sqrt() method 

# import the math module 
import math 

# print the square root of  0 
print(math.sqrt(0)) 

# print the square root of 4
print(math.sqrt(4)) 

# print the square root of 3.5
print(math.sqrt(3.5)) 
```

输出:

```
0.0
2.0
1.8708286933869707

```

**错误:**当 x < 0 时，由于运行时错误，它不执行。

```
# Python3 program to demonstrate the error in 
# sqrt() method 

# import the math module 
import math 

# print the error when x<0 
print(math.sqrt(-1)) 
```

**输出:**

```
Traceback (most recent call last):
  File "/home/67438f8df14f0e41df1b55c6c21499ef.py", line 8, in 
    print(math.sqrt(-1)) 
ValueError: math domain error

```

**实际应用:**给定一个数，检查它是否为素数。
**方法:**运行从 2 到 sqrt(n)的循环，并检查范围(2-sqrt(n))中是否有任何数字除以 n。

```
# Python program for practical application of sqrt() function

# import math module
import math

# function to check if prime or not 
def check(n):
    if n == 1:
        return False

        # from 1 to sqrt(n) 
    for x in range(2, (int)(math.sqrt(n))+1):
        if n % x == 0:
            return False 
    return True

# driver code
n = 23
if check(n):
    print("prime") 
else:
    print("not prime")
```

**输出:**

```
prime

```