# Python 数学库| isfinite()和余数()方法

> 原文:[https://www . geesforgeks . org/python-math-library-is inite-and-余数-method/](https://www.geeksforgeeks.org/python-math-library-isfinite-and-remainder-method/)

Python 有数学库，并且有很多关于它的函数。 **`math.remainder()`** 方法返回一个精确(浮动)值作为余数。

**语法:**

```
math.remainder(x, y)
```

对于有限 x 和有限非零 y，这是差 x–n * y，其中 n 是与商 x / y 的精确值最接近的整数，如果 x / y 正好在两个连续整数的中间，则 n 使用最接近的偶数，因此余数`r = remainder(x, y)`始终满足 abs(r) < = 0.5 * abs(y)。

```
# Importing Math module
import math

# printing remainder of two values
print(math.remainder(5, 2))
print(math.remainder(10, 5))
print(math.remainder(12, 7))
print(math.remainder(6, 2))
```

**输出:**

```
1.0
0.0
-2.0
0.0

```

### math.isfinite()函数–

**语法:**

```
math.isfinite(x)
```

**`math.isfinite()`** 如果 **x** 既不是无穷大也不是 **NaN** ，则方法返回 **True** ，否则返回 **False** 。(注意 0.0 被认为是有限的。)

```
# Importing Math module
import math

# printing remainder of two values
print(math.isfinite(5))
print(math.isfinite(float('nan')))
print(math.isfinite(-2.5))
print(math.isfinite(0.0))
```

**输出:**

```
True
False
True
True

```

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html)