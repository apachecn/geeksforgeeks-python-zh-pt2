# Python | simpy.nextprime()方法

> 原文:[https://www . geesforgeks . org/python-simpy-next prime-method/](https://www.geeksforgeeks.org/python-simpy-nextprime-method/)

在 simpy 模块中，我们可以使用 sympy.nextprime()函数得到给定数 n 的下一个素数。对于 n < 2^64 the answer is definitive; larger n values have a small probability of actually being pseudoprimes. 

```
Syntax:  sympy.nextprime()
Parameter:  n; number to be tested
Return:  next prime value
```

**代码#1:**

## 蟒蛇 3

```
# Python program to get next prime number
# using sympy.nextprime() method

# importing sympy module
from sympy import *

# calling nextprime function on different numbers
nextprime(7)
nextprime(13)
nextprime(2)
```

输出:

```
11
17
3
```

**代码#2:**

## 蟒蛇 3

```
# Python program to check prime number
# using sympy.isprime() method

# importing sympy module
import sympy.ntheory as nt

# calling isprime function on different numbers
nt.nextprime(30)
nt.nextprime(13)
nt.nextprime(2)
```

输出:

```
31
17
3
```