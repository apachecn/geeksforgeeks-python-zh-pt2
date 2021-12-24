# Python 数学库| exp()方法

> 原文:[https://www . geesforgeks . org/python-math-library-exp-method/](https://www.geeksforgeeks.org/python-math-library-exp-method/)

Python 有数学库，有很多关于它的函数。其中一个功能是 **exp()** 。这种方法用来计算 e 的幂，即 e^y，或者我们可以说是 y 的指数..

> **语法:** math.exp(y)
> 
> **参数:**
> *y* 【必选】–它是任何正或负的有效 python 数字。
> 注意，如果 y 的值不是数字，则返回错误。
> 
> **返回:**通过计算 e^y.返回浮点数

**代码# 1:**

```
# Python3 code to demonstrate 
# the working of exp() 
import math 

# initializing the value 
test_int = 4
test_neg_int = -3
test_float = 0.00

# checking exp() values 
# with different numbers
print (math.exp(test_int))
print (math.exp(test_neg_int))
print (math.exp(test_float))
```

**Output:**

```
54.598150033144236
0.049787068367863944
1.0

```

**代码#2:**

```
# Python3 code to demonstrate 
# the working of exp() 
import math 

# checking exp() values 
# with inbuilt numbers
print (math.exp(math.pi))
print (math.exp(math.e))
```

**Output:**

```
23.140692632779267
15.154262241479262

```

**代码#3:** 类型错误

```
# Python3 code to demonstrate 
# the working of exp() 
import math 

# checking for string
print (math.exp("25"))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/c7ae4f1bef0ed8c7756b3f55e7d2ce81.py", line 6, in 
    print (math.exp("25"))
TypeError: a float is required

```