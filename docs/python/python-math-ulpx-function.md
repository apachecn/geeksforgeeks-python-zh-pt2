# Python–数学 ulp(x)函数

> 原文:[https://www.geeksforgeeks.org/python-math-ulpx-function/](https://www.geeksforgeeks.org/python-math-ulpx-function/)

ULP 代表“最后的单位”。math.ulp()是 python 3.9.0 版本中引入的，它返回 float x 的最低有效位的值，在数值分析和计算机科学中，[最小精度的单位(ULP)](https://en.wikipedia.org/wiki/Unit_in_the_last_place#:~:text=In%20computer%20science%20and%20numerical,of%20accuracy%20in%20numeric%20calculations.) 或最后一位的单位是浮点数之间的间距。

**注:**

*   如果参数是 NaN(不是数字)，则输出是 NaN。
*   如果输入 x 为负，输出为 ulp(-x)。
*   如果输入 x 为正无穷大，则输出为 inf。
*   如果输入为零，最小正非规格化可表示浮点就是输出(小于最小正规格化浮点，sys.float_info.min)。
*   如果输入值 x 是最大的正可表示浮点数，则 x 的最低有效位的值就是输出，这样，小于 x 的第一个浮点数就是 x–ulp(x)。
*   否则，如果输入值 x 是一个正的有限数，x 的最低有效位的值就是输出，这样比 x 大的第一个浮点数就是 x + ulp(x)。

> **语法:**数学 ulp(x)
> 
> **参数:**
> 
> x:返回 ulp 的浮点数
> 
> **返回:**
> 
> 返回浮点 x 的最低有效位的值。

**举例:**展示数学 ulp(x)方法的工作原理。

## 蟒蛇 3

```
# python program to explain
# math.ulp(x) for different values of x
import math
import sys

# when x is NaN
x = float('nan')
print(math.ulp(x))

# when x is positive infinity
x = float('inf')
print(math.ulp(x))

# when x is negative infinity
print(math.ulp(-x))

# when x = 0
x = 0.0
print(math.ulp(x))

# when x is maximum representable float
x = sys.float_info.max
print(math.ulp(x))

# x is a positive finite number
x = 5
print(math.ulp(x))

# when x is a negative number
x = -5
print(math.ulp(x))
```

**输出:**

```
nan
inf
inf
5e-324
1.99584030953472e+292
8.881784197001252e-16
8.881784197001252e-16
```