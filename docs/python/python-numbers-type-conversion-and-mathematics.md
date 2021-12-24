# Python 数字、类型转换和数学

> 原文:[https://www . geesforgeks . org/python-numbers-type-conversion-and-mathematics/](https://www.geeksforgeeks.org/python-numbers-type-conversion-and-mathematics/)

**先决条件:** [**Python 语言介绍**](https://www.geeksforgeeks.org/python-language-introduction/)

Python 是一种通用的解释型、交互式、面向对象和高级语言。它是由吉多·范·罗苏姆创造的。它是一种开源编程语言。

### **Python 中的数字类型**

Python 中有三种数字类型:

*   （同 Internationalorganizations）国际组织
*   漂浮物
*   复杂的

由于 Python 是一种松散类型的语言，我们不需要定义变量。数值类型的变量是在给它们赋值时创建的。

**例:**

## 蟒 3

```
# int
var1 = 3

# float
var2 = 3.14

# complex
var3 = 3j

# type() method return the 
# data type of the variable
print(type(var1))
print(type(var2))
print(type(var3))
```

**输出:**

```
<class 'int'>
<class 'float'>
<class 'complex'>
```

### **类型转换**

转换一种数据类型(整数、字符串、浮点等)的值。)转换为另一种数据类型称为类型转换。

**例:**

## 蟒 3

```
# Python code to demonstrate Type conversion 
var1 = 3.14

# type conversion of float to int .
var2 = int(var1) 

print ("After converting float to integer : ", var2) 
print ("type : ",type(var2))

# type conversion of string to integer
var3 = "323"
var4 = int(var3) 

print ("After converting string to integer : ", var4) 
print ("type : ",type(var4))
```

**输出:**

```
After converting float to integer :  3
type :  <class 'int'>
After converting string to integer :  323
type :  <class 'int'>
```

### **对一个** **号**进行算术运算

可以用各种方法对数字进行加减乘除。

<figure class="table">

| **运算符** | **说明** | **示例** |
| +addition | Add values on either side of the operator. | 2+3 = 5 |
| –subtraction | Subtract the right hand value from the left hand value. | 3–2 = 1 |
| * multiplication | Multiply the values on both sides of the operator. | 2 * 3 = 6 |
| /division | Divide two operands. | 3/2 = 1.5 |
| % modulus | Divide two operands and return the remainder. | index | Perform power operation | 3 * * 2 = 9 |
| / | [Floor division](https://www.geeksforgeeks.org/division-operator-in-python/) | 3//2 = 1 |

</figure>

**例:**

## 蟒 3

```
a = 50
b = 30

# Addition of numbers 
add = a + b 

# Subtraction of numbers 
sub = a - b 

# Multiplication of number 
mul = a * b 

# Division of number 
div1 = a / b 

# Division of number 
div2 = a // b 

# Modulo of both number 
mod = a % b 

# Power 
p = a ** b 

# print results 
print(add) 
print(sub) 
print(mul) 
print(div1) 
print(div2) 
print(mod) 
print(p) 
```

**输出:**

```
80
20
1500
1.6666666666666667
1
20
931322574615478515625000000000000000000000000000000
```

### **数学函数:**

数学模块有一组数学函数，其中一些将在下面讨论。

<figure class="table">T25

| **方法** | **描述** |
| math.sqrt() | Returns the square root of a number. |
| 数学。功率() | Returns the value of x to the power of y. |
| 数学。彼尔姆() | Returns the number of ways to select k items from n items in order and without duplication. |
| Rounds a number down to the nearest integer. |
| 数学。天花板() | Rounds a number up to the nearest integer. |
| Math. factorial () | Returns the factorial of a number. |

</figure>

**例 1:**

## 蟒 3

```
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

```
The ceil of 2.3 is : 3
The floor of 2.3 is : 2
```

**例 2:**

## 蟒 3

```
# importing "math" for mathematical operations 
import math 

a = -10
b = 5.5
c = 15
d = 5

# returning the copysigned value. 
print ("The copysigned value of -10 and 5.5 is : ", end="") 
print (math.copysign(5.5, -10)) 

# returning the gcd of 15 and 5 
print ("The gcd of 5 and 15 is : ", end="") 
print (math.gcd(5,15)) 
```

**输出:**

```
The copysigned value of -10 and 5.5 is : -5.5
The gcd of 5 and 15 is : 5
```

要了解更多关于数学函数的知识，你可以参考这篇关于极客伪造者的文章

**随机数:**

在 Python 中，我们有一组用于生成随机数的函数。这些功能用于游戏和彩票应用。

随机库中的方法:

*   select
*   Random range ()
*   random
*   seed

**例:**

## 蟒 3

```
# importing "random" for random operations 
import random 

# using random() to generate a random number 
# between 0 and 1 
print ("A random number between 0 and 1 is : ", end="") 
print (random.random()) 
```

**输出:**

```
A random number between 0 and 1 is : 0.8548698466875713

```

geeksforgeeks 中有一篇关于随机数的详细文章。可以参考这里的文章。