# Python 中的 random.getrandbits()

> 原文:[https://www.geeksforgeeks.org/random-getrandbits-in-python/](https://www.geeksforgeeks.org/random-getrandbits-in-python/)

`random`模块用于在 Python 中生成随机数。实际上不是随机的，而是用来生成伪随机数的。这意味着这些随机生成的数字是可以确定的。

## random.getrandbits()

`random`模块的 **`getrandbits()`** 方法用于返回指定位数的整数。结果中所需的位数在方法中作为参数传递。

**示例:**

```
Input : getrandbits(4)
Output : 14
(the binary equivalent of 14 is 1110 which has 4 bits)

Input : getrandbits(16)
Output : 60431
(the binary equivalent of 14 is 1110110000001111 
which has 16 bits)

```

**例 1:**

```
# import the random module
import random

# a random number with 4 bits
print(random.getrandbits(4))

# a random number with 16 bits
print(random.getrandbits(16))
```

**输出:**

```
10
49195
```

**例 2:**

```
# import the random module
import random

# 5 random number with 4 bits
for i in range(4):
    print(random.getrandbits(4))
```

**输出:**

```
10
0
1
14
```