# Python | simpy.primerange()方法

> 原文:[https://www . geesforgeks . org/python-simpy-prime range-method/](https://www.geeksforgeeks.org/python-simpy-primerange-method/)

在 simpy 模块中，我们可以使用 sympy.primerange()函数得到范围[a，b]内所有素数的 a 列表。

```py
Syntax:  sympy.primerange()
Parameter:  range a and b
Return:  a list of all primes in given range
```

**代码#1:**

## 蟒蛇 3

```py
# Python program to get prime number range
# using sympy.primerange() method

# importing sympy module
from sympy import *

# calling primerange function on different numbers
list(primerange(7, 30))
list(primerange(0, 100))
```

输出:

> 【7、11、13、17、19、23、29】
> 【2、3、5、7、11、13、17、19、23、29、31、37、41、43、47、53、59、61、67、71、73、79、83、89、97】

**代码#2:**

## 蟒蛇 3

```py
# Python program to get the range prime number
# using sympy.primerange() method

# importing sympy module
import sympy.ntheory as nt

# calling primerange function on range
list(nt.primerange(2, 31))
```

输出:

```py
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```