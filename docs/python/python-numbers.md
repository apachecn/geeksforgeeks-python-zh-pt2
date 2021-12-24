# 蟒蛇号

> 原文:[https://www.geeksforgeeks.org/python-numbers/](https://www.geeksforgeeks.org/python-numbers/)

数字数据类型存储数值。它们是不可变的数据类型，这意味着更改数字数据类型的值会导致新分配的对象。

不同类型的数字数据类型有:

*   （同 Internationalorganizations）国际组织
*   漂浮物
*   复杂的

让我们看看他们每个人:

## **Int 类型**

int (Integers) 为整数，包括负数但不包括分数。在 Python 中，整数值可以有多长没有限制。

**示例 1:** 创建 int 并检查类型

## python 3

```
num = -8

# print the data type
print(type(num))
```

**输出:**

```
<class 'int'>
```

**示例 2:** 对 int 类型

执行算术运算

## Python3

```
a = 5
b = 6

# Addition
c = a + b
print("Addition:",c)

d = 9
e = 6

# Subtraction
f = d - e
print("Subtraction:",f)

g = 8
h = 2

# Division
i = g // h
print("Division:",i)

j = 3
k = 5

# Multiplication
l = j * k
print("Multiplication:",l)

m = 25
n = 5

# Modulus
o = m % n

print("Modulus:",o)

p = 6
q = 2

# Exponent
r = p ** q
print("Exponent:",r)
```

**输出:**

```
Addition: 11
Subtraction: 3
Division: 4
Multiplication: 15
Modulus: 0
Exponent: 36
```

## **浮子式**

这是一个用浮点表示的实数。它由小数点指定。可选地，字符 E 或 E 后跟一个正整数或负整数可以被附加以指定科学符号。。表示为浮点数的数字的一些例子是 0.5 和-7.823457。

它们可以通过输入带小数点的数字直接创建，也可以通过对整数进行除法等操作来创建。数字末尾出现的多余零会被自动忽略。

**示例 1:** 创建浮动并检查类型

## 蟒蛇 3

```
num = 3/4

# print the data type
print(type(num))
```

**输出:**

```
<class 'float'>
```

正如我们所看到的，除以任意两个整数都会产生一个浮点数。

一个浮点数也是通过对两个浮点数或一个浮点数和一个整数运行一个操作产生的。

T2T4

```
num = 6 * 7.0

print(type(num))
```

T5

**输出:**

```
<class 'float'>
```

**示例 2:** 对浮点型

执行算术运算

## python 3

```
a = 5.5
b = 3.2

# Addition
c = a + b
print("Addition:", c)

# Subtraction
c = a-b
print("Subtraction:", c)

# Division
c = a/b
print("Division:", c)

# Multiplication
c = a*b
print("Multiplication:", c)
```

**输出**

```
Addition: 8.7
Subtraction: 2.3
Division: 1.71875
Multiplication: 17.6
```

**注意:**一个浮点数的精度最多只有小数点后 15 位，第 16 位可以不准确。

## **复合型**

复数是由实部和虚部组成的数。例如，2 + 3j 是复数，其中 2 是实部，3 乘以 j 是虚部。

**示例 1:** 创建复杂和检查类型

## python 3

```
num = 6 + 9j

print(type(num))
```

**输出:**

```
<class 'complex'>
```

**示例 2:** 对复杂类型

执行算术运算

## Python3

```
a = 1 + 5j
b = 2 + 3j

# Addition
c = a + b
print("Addition:",c)

d = 1 + 5j
e = 2 - 3j

# Subtraction
f = d - e
print("Subtraction:",f)

g = 1 + 5j
h = 2 + 3j

# Division
i = g / h
print("Division:",i)

j = 1 + 5j
k = 2 + 3j

# Multiplication
l = j * k
print("Multiplication:",l)
```

**输出:**

```
Addition: (3+8j)
Subtraction: (-1+8j)
Division: (1.307692307692308+0.5384615384615384j)
Multiplication: (-13+13j)
```

## **数字间的类型转换**

我们可以通过两种方法将一个数字转换成另一个形式:

*   **Using arithmetic operation:** If one of the operands is a floating-point number, we can implicitly (automatically) change the type of the number by using operations such as addition and subtraction. This method does not apply to plural numbers.

**示例:**使用算术运算进行类型转换

## python 3

```
a = 1.6
b = 5

c = a + b

print(c)
```

**输出:**

```
6.6
```

*   **Using built-in functions:** We can also use built-in functions such as int (), float () and complex () to explicitly convert to different types.

**示例:**使用内置功能的类型转换

## python 3

```
a = 2
print(float(a))

b = 5.6
print(int(b))

c = '3'
print(type(int(c)))

d = '5.6'
print(type(float(c)))

e = 5
print(complex(e))

f = 6.5
print(complex(f))
```

**输出:**

```
2.0
5
<class 'int'>
<class 'float'>
(5+0j)
(6.5+0j)
```

当我们将浮点转换为 int 时，小数部分被截断。

**注意:**

1.  We can't convert a complex data type number into int data type and float data type number.
2.  We can't apply complex built-in functions to strings.

## Python 中的十进制数

对浮点数进行算术运算会得到一些意想不到的结果。让我们考虑一个我们想要将 1.1 添加到 2.2 的情况。你们一定都想知道这个操作的结果应该是 3.3，但是让我们看看 Python 给出的输出。

**例:**

## 蟒 3

```
a = 1.1
b = 2.2
c = a+b

print(c)
```

**输出:**

```
3.3000000000000003
```

你能得到意想不到的结果。让我们考虑另一种情况，我们将减去 1.2 和 1.0。同样，我们将期望结果为 0.2，但是让我们看看 Python 给出的输出。

**例:**

## 蟒 3

```
a = 1.2
b = 1.0
c = a-b

print(c)
```

**输出:**

```
0.19999999999999996
```

你们一定都认为 Python 有问题，但事实并非如此。这与 Python 关系不大，更多的是与底层平台如何处理浮点数有关。这是在系统内部处理浮点数时遇到的正常情况。这是浮点数内部表示时引起的问题，浮点数使用固定数量的二进制数字来表示十进制数字。用二进制表示一些十进制数是很困难的，所以在很多情况下，会导致很小的舍入误差。

在这种情况下，以 1.2 为例，0.2 在二进制中的表示为 0.00110011001100110011001100……以此类推。很难在内部存储这个无限小数。通常，浮点对象的值以固定精度(通常为 53 位)存储在二进制浮点中。所以我们在内部将 1.2 表示为，

```
1.0011001100110011001100110011001100110011001100110011  
```

正好等于:

```
1.1999999999999999555910790149937383830547332763671875
```

对于这种情况，Python 的十进制模块来拯救。如前所述，浮点数的精度只有 15 位，但在十进制数中，精度是用户定义的。它对浮点数的运算方式和我们在学校里学的一样。让我们看看上面两个例子，试着用十进制数来求解。

**示例:**

## 蟒蛇 3

```
import decimal

a = decimal.Decimal('1.1')
b = decimal.Decimal('2.2')

c = a+b
print(c)
```

**Output**

```
3.3
```

**我们可以使用十进制模块来处理以下情况–**

*   When we want to define the required precision by ourselves
*   For financial applications requiring accurate decimal representation

**注:**关于 Python 中的十进制数以及本模块提供的函数的更多信息，请参考[Python 中的十进制函数](https://www.geeksforgeeks.org/decimal-functions-python-set-1/)

## Python 中的随机数

Python 提供了一个[随机模块](https://www.geeksforgeeks.org/python-random-module/)来生成伪随机数。这个模块可以创建随机数，在 Python 中从序列中选择一个随机元素，等等。

**例 1:** 创造随机值

T5】python 3T7

```
import random

print(random.random())
```

T8T10**输出**T1

**例 2:** 从字符串或列表中选择随机元素

T5】python 3T0T10**输出**

```
f
0
```

T13】

**注:**关于随机数的更多信息，请参考我们的[随机数教程](https://www.geeksforgeeks.org/python-random-module/)

## Python 数学

Python 的[数学模块](https://www.geeksforgeeks.org/python-math-module/)帮助进行不同的数学运算三角、统计、概率、对数等。

**例:**

## 蟒 3

```
# importing "math" for mathematical operations
import math

a = 3.5

# returning the ceil of 3.5
print ("The ceil of 3.5 is : ", end="")
print (math.ceil(a))

# returning the floor of 3.5
print ("The floor of 3.5 is : ", end="")
print (math.floor(a))

# find the power
print ("The value of 3.5**2 is : ",end="")
print (pow(a,2))

# returning the log2 of 16
print ("The value of log2 of 3.5 is : ", end="")
print (math.log2(a))

# print the square root of 3.5
print ("The value of sqrt of 3.5 is : ", end="")
print(math.sqrt(a))

# returning the value of sine of 3.5
print ("The value of sine of 3.5 is : ", end="")
print (math.sin(a))
```

**输出**

```
The ceil of 3.5 is : 4
The floor of 3.5 is : 3
The value of 3.5**2 is : 12.25
The value of log2 of 3.5 is : 1.8073549220576042
The value of sqrt of 3.5 is : 1.8708286933869707
The value of sine of 3.5 is : -0.35078322768961984
```

**注意:**关于 Python 数学模块的更多信息，请参考我们的[数学模块教程。](https://www.geeksforgeeks.org/python-math-module/)