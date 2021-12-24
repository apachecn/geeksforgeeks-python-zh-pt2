# Python | simpy.prevprime()方法

> 原文:[https://www . geesforgeks . org/python-simpy-prev prime-method/](https://www.geeksforgeeks.org/python-simpy-prevprime-method/)

在 simpy 模块中，我们可以使用 sympy.prevprime()函数得到给定数 n 的前一个素数。对于 n < 2^64 the answer is definitive; larger n values have a small probability of actually being pseudoprimes. 

```
Syntax:  sympy.prevprime()
Parameter:  n; number to be tested
Return:  previous prime value
```

**代码#1:**

## 蟒蛇 3

```
# Python program to get previous prime number
# using sympy.prevprime() method

# importing sympy module
from sympy import *

# calling prevprime function on different numbers
prevprime(7)
prevprime(13)
```

输出:

```
5
11
```

**代码#2:**

## 蟒蛇 3

```
# Python program to check prime number
# using sympy.prevprime() method

# importing sympy module
import sympy.ntheory as nt

# calling prevprime function on different numbers
nt.prevprime(2)
```

输出:

```
ValueError: no preceding primes
```