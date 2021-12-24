# Python 数学库| expm1()方法

> 原文:[https://www . geesforgeks . org/python-math-library-expm 1-method/](https://www.geeksforgeeks.org/python-math-library-expm1-method/)

Python 有*数学库*，并且有很多关于它的功能。其中一个功能就是 **`expm1()`** 。该函数从数学上计算`exp(x) - 1`的值。如果我们需要计算这个值，可以使用这个方法。

> **语法:** math.expm1()
> 
> **参数:**
> **x :** 必须计算其 exp(x)-1 的数。
> 
> **返回:**返回“exp(x)-1”的计算值

**代码#1 :** 演示 expm1()的工作

```
# Python3 code to demonstrate
# the working of expm1()
import math

# initializing the value 
test_int = 4
test_neg_int = -3

# checking expm1() values
# doesn't throw error with negative
print ("The expm1 value using positive integer : "
                      + str(math.expm1(test_int)))

print ("The expm1 value using negative integer : "
                  + str(math.expm1(test_neg_int)))
```

**输出:**

```
The expm1 value using positive integer : 53.598150033144236
The expm1 value using negative integer : -0.950212931632136
```

**“exp() – 1” vs “expm1()”**

如果我们总是能计算出 exp()，然后从中减去 1，那么就会有一个问题为什么`expm1()`方法会被创造出来。第一个原因是数值`exp() - 1`在数学和科学应用以及公式中被大量使用。
最重要的原因是，对于小于 e-10 的 x 的较小值，`expm1()`方法给出的结果比`exp() - 1`更准确。

**代码#2 :** 比较 expm1()和 exp()-1

```
# Python3 code to demonstrate
# the application of expm1()
import math

# initializing the value 
test_int = 1e-10

# checking expm1() values
# expm1() is more accurate
print ("The value with exp()-1  : " + str(math.exp(test_int)-1))
print ("The value with expm1() : " + str(math.expm1(test_int)))
```

**输出:**

```
The value with exp()-1  : 1.000000082740371e-10
The value with expm1() : 1.00000000005e-10

```