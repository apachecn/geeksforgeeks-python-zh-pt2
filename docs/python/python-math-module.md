# Python 数学模块

> 原文:[https://www.geeksforgeeks.org/python-math-module/](https://www.geeksforgeeks.org/python-math-module/)

有时，当处理某种金融或科学项目时，有必要在项目中实施数学计算。Python 提供了**数学模块**来处理这样的计算。数学模块提供了处理基本运算(如加法(+)、减法(-)、乘法(*)、除法(/)和高级运算(如三角函数、对数函数、指数函数)的功能。

在本文中，我们从基础知识开始学习数学模块，并借助一个巨大的数据集来推进，该数据集包含借助好例子解释的函数。

## 数学模块提供的常数

数学模块提供各种[常数](https://www.geeksforgeeks.org/constants-of-maths-in-python/)的值，如π、τ。拥有这样的常数可以节省我们每次使用它时写入每个常数值的时间，而且非常精确。数学模块提供的常数有–

*   欧拉数
*   圆周率
*   希腊语的第十九个字母
*   无穷
*   不是数字(NaN)

让我们详细看看每个常数。

### **欧拉数**

数学常数返回欧拉数:2.71828182846。

**语法:**

> 数学 e

**示例:**

## 蟒蛇 3

```py
# Import math Library
import math

# Print the value of Euler e
print (math.e)
```

**输出:**

```py
2.718281828459045
```

### 圆周率

你们一定都熟悉圆周率。圆周率表示为 22/7 或 3.14。**数学π**为π提供了更精确的值。

**语法:**

> 数学. pi

**例 1:**

## 蟒蛇 3

```py
# Import math Library
import math

# Print the value of pi
print (math.pi)
```

**输出:**

```py
3.141592653589793
```

**例 2:** 我们来找圆的面积

## 蟒蛇 3

```py
# Import math Library
import math

# radius of the circle
r = 4

# value of pie
pie = math.pi

# area of the circle
print(pie * r * r)
```

**输出:**

```py
50.26548245743669
```

### 希腊语的第十九个字母

[**τ**](https://www.geeksforgeeks.org/tau-mathematical-constant/)定义为圆周与圆半径的比值。**数学τ**常数返回τ:6 的值。58860 . 88888888861

**语法:**

> 数学τ

**示例:**

## 蟒蛇 3

```py
# Import math Library
import math

# Print the value of tau
print (math.tau)
```

**输出:**

```py
6.283185307179586
```

### 无穷

无限基本上是指从正反两个方向看都是永无止境或无边无际的东西。它不能用数字来描述。数学 inf 常数返回正无穷大。对于负无穷大，使用 **-math.inf** 。

**语法:**

> 数学. inf

**例 1:**

## 蟒蛇 3

```py
# Import math Library
import math

# Print the positive infinity
print (math.inf)

# Print the negative infinity
print (-math.inf)
```

**输出:**

```py
inf
-inf
```

**示例 2:** 将无穷大的值与最大浮点值进行比较

## 蟒蛇 3

```py
# Import math Library
import math

print (math.inf > 10e108)
print (-math.inf < -10e108)
```

**输出:**

```py
True
True
```

### 圆盘烤饼

**math.nan** 常量返回一个浮点 nan(不是数字)值。该值不是合法数字。nan 常数相当于 float(“nan”)。

**示例:**

## 蟒蛇 3

```py
# Import math Library
import math

# Print the value of nan
print (math.nan)
```

**输出:**

```py
nan
```

## 数字函数

在这一节中，我们将讨论与数论和表示论一起使用的函数，例如求一个数的阶乘。

### 找出天花板和地板的价值

天花板值表示大于数字的最小积分值，地板值表示小于数字的最大积分值。这可以分别使用 [**【天花板】(**](https://www.geeksforgeeks.org/python-math-ceil-function/) )和 [**地板()**](https://www.geeksforgeeks.org/python-math-floor-function/) 方法轻松计算。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# ceil() and floor()

# importing "math" for mathematical operations
import math

a = 2.3

# returning the ceil of 2.3
print ("The ceil of 2.3 is : ", end="")
print (math.ceil(a))

# returning the floor of 2.3
print ("The floor of 2.3 is : ", end="")
print (math.floor(a))
```

**输出:**

```py
The ceil of 2.3 is : 3
The floor of 2.3 is : 2
```

### 求数字的阶乘

使用 [**阶乘()**](https://www.geeksforgeeks.org/python-math-factorial-function/) 函数我们可以在单行代码中找到一个数字的阶乘。如果数字不是整数，将显示一条错误消息。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# factorial()

# importing "math" for mathematical operations
import math

a = 5

# returning the factorial of 5
print("The factorial of 5 is : ", end="")
print(math.factorial(a))
```

**输出:**

```py
The factorial of 5 is : 120
```

### 找到 GCD

[**【gcd()】**](https://www.geeksforgeeks.org/python-math-gcd-function/)**函数用来求作为自变量传递的两个数的最大公约数。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate the working of
# gcd()

# importing "math" for mathematical operations
import math

a = 15
b = 5

# returning the gcd of 15 and 5
print ("The gcd of 5 and 15 is : ", end="")
print (math.gcd(b, a))
```

****输出:****

```py
The gcd of 5 and 15 is : 5
```

### **求绝对值**

**[**fabs()**](https://www.geeksforgeeks.org/python-math-fabs-function/) 函数返回数字的绝对值。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate the working of
# fabs()

# importing "math" for mathematical operations
import math

a = -10

# returning the absolute value.
print ("The absolute value of -10 is : ", end="")
print (math.fabs(a))
```

****输出:****

```py
The absolute value of -10 is : 10.0
```

**参考下面的文章来获得关于数字函数的详细信息。**

*   **[Python 中的数学函数|集合 1(数值函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/)**

## **对数和幂函数**

**幂函数可以表示为 x^n，其中 n 是 x 的幂，而对数函数被认为是指数函数的反函数。**

### **发现经验的力量**

**[exp()](https://www.geeksforgeeks.org/python-math-library-exp-method/) 方法用来计算 e 的幂，即![e^y        ](img/8b1b6767548afda77ff02c98fc4efccc.png "Rendered by QuickLaTeX.com")或者我们可以说 y 的指数**

****示例:****

## **蟒蛇 3**

```py
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

****输出:****

```py
54.598150033144236
0.049787068367863944
1.0
```

### **求一个数的幂**

**[**pow()**](https://www.geeksforgeeks.org/pow-in-python/) 函数计算 x**y，该函数首先将其参数转换为 float，然后计算 pow。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate pow()
# version 1

print ("The value of 3**4 is : ",end="")

# Returns 81
print (pow(3,4))
```

****输出:****

```py
The value of 3**4 is : 81.0
```

### **求对数**

*   ****log()** 函数返回以 b 为基数的 a 的对数值，如果没有提到基数，则计算值为自然对数。**
*   ****log2(a)** 函数计算基数为 2 的 log a 的值。这个值比上面讨论的函数值更精确。**
*   ****log10(a)** 函数计算基数为 10 的 log a 的值。这个值比上面讨论的函数值更精确。**

## **蟒蛇 3**

```py
# Python code to demonstrate the working of
# logarithm

# importing "math" for mathematical operations
import math

# returning the log of 2,3
print ("The value of log 2 with base 3 is : ", end="")
print (math.log(2,3))

# returning the log2 of 16
print ("The value of log2 of 16 is : ", end="")
print (math.log2(16))

# returning the log10 of 10000
print ("The value of log10 of 10000 is : ", end="")
print (math.log10(10000))
```

****输出:****

```py
The value of log 2 with base 3 is : 0.6309297535714574
The value of log2 of 16 is : 4.0
The value of log10 of 10000 is : 4.0
```

### **求平方根**

**[**sqrt()**](https://www.geeksforgeeks.org/python-math-function-sqrt/) 函数返回数字的平方根。**

****示例:****

## **蟒蛇 3**

```py
# Python3 program to demonstrate the
# sqrt() method

# import the math module
import math

# print the square root of 0
print(math.sqrt(0))

# print the square root of 4
print(math.sqrt(4))

# print the square root of 3.5
print(math.sqrt(3.5))
```

****输出:****

```py
0.0
2.0
1.8708286933869707
```

**请参考下面的文章，获取关于对数函数和幂函数的详细信息**

*   **[Python 中的数学函数|集合 2(对数和幂函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-2-logarithmic-power-functions/)**

## **三角函数和角函数**

**你们都必须了解三角函数，以及如何很难找到任何角度的正弦值和余弦值。数学模块提供内置函数来查找这些值，甚至在度数和弧度之间改变这些值。**

### **求正弦、余弦和正切**

****sin()、cos()和 tan()** 函数返回作为参数传递的值的正弦、余弦和正切值。这个函数传递的值应该是**弧度**。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate the working of
# sin(), cos(), and tan()

# importing "math" for mathematical operations
import math

a = math.pi/6

# returning the value of sine of pi/6
print ("The value of sine of pi/6 is : ", end="")
print (math.sin(a))

# returning the value of cosine of pi/6
print ("The value of cosine of pi/6 is : ", end="")
print (math.cos(a))

# returning the value of tangent of pi/6
print ("The value of tangent of pi/6 is : ", end="")
print (math.tan(a))
```

****输出:****

```py
The value of sine of pi/6 is : 0.49999999999999994
The value of cosine of pi/6 is : 0.8660254037844387
The value of tangent of pi/6 is : 0.5773502691896257
```

### **将角度值转换为弧度值，反之亦然**

*   ****degrees()** 函数用于将参数值从弧度转换为度数。**
*   ****弧度()**函数用于将参数值从度数转换为弧度。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate the working of
# degrees() and radians()

# importing "math" for mathematical operations
import math

a = math.pi/6
b = 30

# returning the converted value from radians to degrees
print ("The converted value from radians to degrees is : ", end="")
print (math.degrees(a))

# returning the converted value from degrees to radians
print ("The converted value from degrees to radians is : ", end="")
print (math.radians(b))
```

****输出:****

```py
The converted value from radians to degrees is : 29.999999999999996
The converted value from degrees to radians is : 0.5235987755982988
```

**参考下面的文章来获得三角函数和角函数的详细信息。**

*   **[Python 中的数学函数|集合 3(三角函数和角函数)](https://www.geeksforgeeks.org/mathematical-functions-in-python-set-3-trigonometric-and-angular-functions/)**

## **特殊功能**

**除了我们已经讨论过的所有数值、对数函数之外，数学模块还提供了一些更有用的函数，这些函数不属于上面讨论的任何类别，但在编码时可能会变得很方便。**

### **查找伽马值**

**[**gamma()**](https://www.geeksforgeeks.org/python-math-library-gamma-function/) 函数用于返回参数的 gamma 值。**

****示例:****

## **蟒蛇 3**

```py
# Python code to demonstrate
# working of gamma()
import math

# initializing argument
gamma_var = 6

# Printing the gamma value.
print ("The gamma value of the given argument is : "
                    + str(math.gamma(gamma_var)))
```

****输出:****

```py
The gamma value of the given argument is : 120.0
```

### **检查该值是无穷大还是 NaN**

****isinf()** 功能用于检查数值是否无穷大。**

****示例:****

## **蟒蛇 3**

```py
# Python3 code to demonstrate
# the working of isnan()
import math

# checking isnan() values
# with inbuilt numbers
print (math.isinf(math.pi))
print (math.isinf(math.e))

# checking for NaN value
print (math.isinf(float('inf')))
```

****输出:****

```py
False
False
True
```

**[**isnan()**](https://www.geeksforgeeks.org/python-math-library-isnan-method/) 如果数字为“nan”则函数返回 true，否则返回 false。**

****示例:****

## **蟒蛇 3**

```py
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

****输出:****

```py
False
False
True
```

**参考下面的文章来获得关于特殊功能的详细信息。**

*   **[Python 中的数学函数|集合 4(特殊函数和常数)](https://www.geeksforgeeks.org/mathematical-functions-in-python-set-4-special-functions-and-constants/)**

**Python 中的数学函数列表**

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| [天花板(x)](https://www.geeksforgeeks.org/python-math-ceil-function/) | 返回大于该数的最小整数值 |
| [copysign(x，y)](https://www.geeksforgeeks.org/python-math-function-copysign/) | 返回值为“x”但符号为“y”的数字 |
| [晶圆厂(x)](https://www.geeksforgeeks.org/python-math-fabs-function/) | 返回数字的绝对值 |
| [因子(x)](https://www.geeksforgeeks.org/python-math-factorial-function/) | 返回数字的阶乘 |
| [楼层(x)](https://www.geeksforgeeks.org/python-math-floor-function/) | 返回小于该数的最大整数值 |
| [gcd(x，y)](https://www.geeksforgeeks.org/python-math-gcd-function/) | 计算两个数的最大公约数 |
| [fmod（x， y）](https://www.geeksforgeeks.org/python-fmod-function/) | 当 x 除以 y 时返回余数 |
| [frexp(x)](https://www.geeksforgeeks.org/python-frexp-function/) | 以对的形式返回 x 的尾数和指数(m，e) |
| [fsum(可滴定)](https://www.geeksforgeeks.org/python-fsum-function/) | 返回可迭代表中元素和的精确浮点值 |
| isfinite(x) | 检查该值是否既不是无穷大也不是南 |
| isinf(x) | 检查该值是否为无穷大 |
| [isnan（x）](https://www.geeksforgeeks.org/python-math-library-isnan-method/) | 如果数字为“nan”则返回真，否则返回假 |
| [ldxp(x，i)](https://www.geeksforgeeks.org/python-ldexp-function/) | 返回 x * (2**i) |
| [modf(x)](geeksforgeeks.org/python-modf-function/) | 返回 x 的小数部分和整数部分 |
| [truc(x)](https://www.geeksforgeeks.org/g-fact-35-truncate-in-python/) | 返回 x 的截断整数值 |
| [exp(x)](https://www.geeksforgeeks.org/python-math-library-exp-method/) | 返回 e 的值乘以 x 的幂(e**x) |
| [露出 1(x)](https://www.geeksforgeeks.org/python-math-library-expm1-method/) | 返回 e 的值乘以 a (x-1)的幂 |
| 日志(x[，b]) | 返回以 b 为基数的 a 的对数值 |
| log1p(x) | 返回 1+x 的自然对数值 |
| log2(x) | 计算基数为 2 的日志 a 的值 |
| log10(x) | 计算基数为 10 的对数 a 的值 |
| [幂(x，y)](https://www.geeksforgeeks.org/pow-in-python/) | 计算 x 的值乘以 y 的幂(x**y) |
| [sqrt(x)](https://www.geeksforgeeks.org/python-math-function-sqrt/) | 返回数字的平方根 |
| [acos(x)](https://www.geeksforgeeks.org/python-math-acos-function/) | 返回作为参数传递的值的余弦值 |
| [asin(x)](https://www.geeksforgeeks.org/python-math-asin-function/) | 返回作为参数传递的值的反正弦 |
| [阿坦(x)](https://www.geeksforgeeks.org/python-math-atan-function/) | 返回作为参数传递的值的反正切 |
| [atan2(y，x)](https://www.geeksforgeeks.org/atan2-function-python/) | 返回一个整数(y / x) |
| [cos(x)](https://www.geeksforgeeks.org/python-math-cos-function/) | 返回作为参数传递的值的余弦值 |
| [海波(x，y)](https://www.geeksforgeeks.org/python-math-function-hypot/) | 返回参数中传递的值的斜边 |
| [sin(x)](https://www.geeksforgeeks.org/python-math-sin-function/) | 返回作为参数传递的值的正弦值 |
| [tan(x)](https://www.geeksforgeeks.org/python-math-tan-function/) | 返回作为参数传递的值的正切值 |
| 度数(x) | 将参数值从弧度转换为度数 |
| 弧度（x） | 将参数值从度数转换为弧度 |
| [acosh(x)](https://www.geeksforgeeks.org/python-math-acosh-function/) | 返回作为参数传递的值的反双曲余弦值 |
| 正在使用一个精确的描述方式绘制一个 1231 处分布的样子 | 返回作为参数传递的值的反双曲正弦值 |
| [阿坦(x)](https://www.geeksforgeeks.org/python-math-atanh-function/) | 返回作为参数传递的值的反双曲正切值 |
| [cosh(x)](https://www.geeksforgeeks.org/python-math-cosh-function/) | 返回作为参数传递的值的双曲余弦值 |
| [sinh(x)](https://www.geeksforgeeks.org/python-math-sinh-function/) | 返回作为参数传递的值的双曲正弦值 |
| [tanh(x)](https://www.geeksforgeeks.org/python-math-tanh-function/) | 返回作为参数传递的值的双曲正切值 |
| 电流变流体(x) | 返回 x 处的错误函数 |
| erfc(x) | 返回 x 处的互补误差函数 |
| [伽玛(x)](https://www.geeksforgeeks.org/python-math-library-gamma-function/) | 返回参数的伽马函数 |
| 真(x) | 返回伽玛函数绝对值的自然对数 |

</figure>