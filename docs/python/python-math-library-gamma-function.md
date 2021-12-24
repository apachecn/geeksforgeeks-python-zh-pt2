# Python 数学γ()方法

> 原文:[https://www . geesforgeks . org/python-math-library-gamma-function/](https://www.geeksforgeeks.org/python-math-library-gamma-function/)

Python 在其语言中允许各种数学运算，这在科学领域有着多方面的应用。Python 提供的一个这样的功能是内置的 **`gamma()`** 函数，该函数用数字计算函数中传递的数字的伽马值。

> **语法:**数学γ(x)
> **参数:**
> **x :** 需要计算其γ值的数字。
> 
> **返回:**伽马值，数值等于“阶乘(x-1)”。

**代码#1 :** 演示伽马()的工作

```
# Python code to demonstrate
# working of gamma()
import math

# initializing argument
gamma_var = 6

# Printing the gamma value.
print ("The gamma value of the given argument is : "
                       + str(math.gamma(gamma_var)))
```

**输出:**

```
The gamma value of the given argument is : 120.0
```

**factorial() vs gamma()**

伽马值也可以使用`factorial(x-1)`找到，但是`gamma()`的用例是因为，如果我们比较两个函数来实现相似的任务，`gamma()`提供了更好的性能。

**代码#2 :** 比较`factorial()`和`gamma()`

```
# Python code to demonstrate
# factorial() vs gamma()
import math
import time 

# initializing argument
gamma_var = 6

# checking performance 
# gamma() vs factorial()
start_fact = time.time()
res_fact = math.factorial(gamma_var-1)

print ("The gamma value using factorial is : " 
                              + str(res_fact))

print ("The time taken to compute is : "
        + str(time.time() - start_fact))

print ('\n')

start_gamma = time.time()
res_gamma = math.gamma(gamma_var)

print ("The gamma value using gamma() is : "
                           + str(res_gamma))

print ("The time taken to compute is : " 
       + str(time.time() - start_gamma))
```

**输出:**

```
The gamma value using factorial is : 120
The time taken to compute is : 9.059906005859375e-06

The gamma value using gamma() is : 120.0
The time taken to compute is : 5.245208740234375e-06

```