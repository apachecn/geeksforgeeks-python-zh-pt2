# Python 数学库| isnan()方法

> 原文:[https://www . geesforgeks . org/python-math-library-isnan-method/](https://www.geeksforgeeks.org/python-math-library-isnan-method/)

Python 有`**math**` 库，关于它有很多功能。其中一个功能就是`**isnan()**`。此方法用于检查给定参数是否为有效数字。

> **语法:** math.isnan(x)
> 
> **参数:**
> **x** 【必选】:任意有效的 python 数据类型或任意数字。
> 
> **返回:**返回类型为布尔值。
> **- >** 如果给定参数为任意数字(正或负)
> **- >** 则返回**如果给定参数为 NaN(非数字)，则返回**真**。**

**代码#1:**

```
# Python3 code to demonstrate 
# the working of isnan() 
import math 

# initializing the value 
test_int = 4
test_neg_int = -3
test_float = 0.00

# checking isnan() values 
# with different numbers
print (math.isnan(test_int))
print (math.isnan(test_neg_int))
print (math.isnan(test_float))
```

**Output:**

```
False
False
False

```

**代码#2:**

```
# Python3 code to demonstrate 
# the working of isnan() 
import math 

# checking isnan() values 
# with inbuilt numbers
print (math.isnan(math.pi))
print (math.isnan(math.e))

# checking for NaN value
print (math.isnan(float('nan')))
```

**Output:**

```
False
False
True

```