# Python 运算符

> 原文:[https://www.geeksforgeeks.org/python-operators/](https://www.geeksforgeeks.org/python-operators/)

**Python 运算符**一般用于对值和变量进行运算。这些是用于逻辑和算术运算的标准符号。在本文中，我们将研究不同类型的 Python 运算符。

## **算术运算符**

[算术运算符](https://www.geeksforgeeks.org/python-arithmetic-operators/)用于执行加法、减法、乘法和除法等数学运算。

<figure class="table">

| 操作员 | 描述 | 语法 |
| --- | --- | --- |
| + | 加法:将两个操作数 | x+y |
| – | 减法:减去两个操作数 | x–y |
| * | 乘法:将两个操作数 | x * y |
| / | 除法(浮点):将第一个操作数相乘 | 除法(地板):将第一个操作数除以第二个 | x//y |
| % | 模数:返回第一个操作数除以第二个 | 时的余数 x % y |
| * * | 幂:返回第一个升到幂的第二个 | x ** y |

</figure>

### **示例:Python 中的算术运算符**

## 蟒蛇 3

```
# Examples of Arithmetic Operator
a = 9
b = 4

# Addition of numbers
add = a + b

# Subtraction of numbers
sub = a - b

# Multiplication of number
mul = a * b

# Division(float) of number
div1 = a / b

# Division(floor) of number
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

**Output**

```
13
5
36
2.25
2
1
6561
```

**注:**关于这两个运算符的一些有趣的事实，请参考/和// 之间的[差异。](https://www.geeksforgeeks.org/benefits-of-double-division-operator-over-single-division-operator-in-python/)

## 对比**操作员**

[比较](https://www.geeksforgeeks.org/relational-operators-in-python/)[关系运算符](https://www.geeksforgeeks.org/relational-operators-in-python/)的比较这些值。根据情况返回**真**或**假**。

<figure class="table">

| 操作员 | 描述 | 语法 |
| --- | --- | --- |
| > | 大于:如果左操作数大于右操作数则为 True | x>y |
| < | 小于:如果左操作数小于右操作数则为 True | x< |
| = | 等于:如果两个操作数相等则为 True | x = = y= | 不等于–如果操作数不相等则为 True | x！= y |
| >= | 大于或等于真如果左操作数大于或等于右 | x>= y |
| <= | 小于或等于真如果左操作数小于或等于右 | x<= y |

</figure>

### **示例:Python 中的比较运算符**

## 蟒蛇 3

```
# Examples of Relational Operators
a = 13
b = 33

# a > b is False
print(a > b)

# a < b is True
print(a < b)

# a == b is False
print(a == b)

# a != b is True
print(a != b)

# a >= b is False
print(a >= b)

# a <= b is True
print(a <= b)
```

**Output**

```
False
True
False
True
False
True
```

## **逻辑运算符**

[逻辑运算符](https://www.geeksforgeeks.org/python-logical-operators-with-examples-improvement-needed/)执行**逻辑与**、**逻辑或**和**逻辑非**运算。它用于组合条件语句。

<figure class="table">

| 操作员 | 描述 | 语法 |
| --- | --- | --- |
| 和 | 逻辑与:如果两个操作数都为真则为真 | x 和 y |
| 或 | 逻辑或:如果其中一个操作数为真则为真 | x 或 y |
| 非 | 逻辑非:如果操作数为假则为真 | 非 x |

</figure>

### 示例:Python 中的逻辑运算符

## 蟒蛇 3

```
# Examples of Logical Operator
a = True
b = False

# Print a and b is False
print(a and b)

# Print a or b is True
print(a or b)

# Print not a is False
print(not a)
```

**Output**

```
False
True
False
```

## **按位运算符**

[位运算符](https://www.geeksforgeeks.org/python-bitwise-operators/)作用于位并执行逐位运算。这些用于对二进制数进行运算。

<figure class="table">T10】|

| 操作员 | 描述 | 语法 |
| --- | --- | --- |
| & | 按位 and | x&y |
| 按位 or | x &#124; y |
| ~ | 按位 not | ~ x |
| ^ | 按位异或 | x ^ y【 |

</figure>

### 示例:Python 中的按位运算符

## 蟒蛇 3

```
# Examples of Bitwise operators
a = 10
b = 4

# Print bitwise AND operation
print(a & b)

# Print bitwise OR operation
print(a | b)

# Print bitwise NOT operation
print(~a)

# print bitwise XOR operation
print(a ^ b)

# print bitwise right shift operation
print(a >> 2)

# print bitwise left shift operation
print(a << 2)
```

**Output**

```
0
14
-11
14
2
40
```

## **分配操作员**

[赋值运算符](https://www.geeksforgeeks.org/assignment-operators-in-python/)用于给变量赋值。

<figure class="table">a/= b a/bT42】% =

| 操作员 | 描述 | 语法 |
| --- | --- | --- |
| = | 将表达式右侧的值赋值给左侧操作数 | x = y+z |
| += | 相加 and:将右侧操作数与左侧操作数相加，然后赋值给左侧操作数 | a+= b a+b |
| -= | AND:从左侧操作数减去右侧操作数，然后赋值给左侧操作数 | 乘法 and:将右操作数与左操作数相乘，然后分配给左操作数 | a * = b a = a * b |
| /= | 除法 and:将左操作数与右操作数相除，然后分配给左操作数 |
| 模数 AND:使用左右操作数取模，然后分配结果 and:用右操作数除左操作数，然后将值(floor)赋给左操作数 | a/= b a = a//b |
| * * = | 指数 AND:计算指数(提升幂) 值使用操作数并将值赋给左操作数 | a * * = b a = a * * b |
| &= | 对操作数执行按位“与”并将值赋给左操作数 | a&= b a = a&b |
| &#124; = | 对操作数和执行按位“或” | a^=b a=a^b |
| >>= | 对操作数执行按位右移并将值赋给左操作数 | a>>= b a>>b |
| <<= | 对操作数执行按位左移并将值赋给 |

</figure>

### 示例:Python 中的赋值运算符

## 蟒蛇 3

```
# Examples of Assignment Operators
a = 10

# Assign value
b = a
print(b)

# Add and assign value
b += a
print(b)

# Subtract and assign value
b -= a
print(b)

# multiply and assign
b *= a
print(b)

# bitwise lishift operator
b <<= a
print(b)
```

**Output**

```
10
20
10
100
102400
```

## **身份操作员**

**是****不是**是[身份运算符](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)两者都用于检查两个值是否位于内存的同一部分。两个相等的变量并不意味着它们是相同的。

```
is          True if the operands are identical 
is not      True if the operands are not identical 
```

### **示例:身份运算符**

## 蟒蛇 3

```
a = 10
b = 20
c = a

print(a is not b)
print(a is c)
```

**Output**

```
True
True
```

## **会员运营商**

的**和不在**的**是会员运营商；用于测试值或变量是否在序列中。**

```
**in**            True if value is found in the sequence
**not in**        True if value is not found in the sequence
```

### **示例:**成员资格**操作员**

## 蟒蛇 3

```
# Python program to illustrate
# not 'in' operator
x = 24
y = 20
list = [10, 20, 30, 40, 50]

if (x not in list):
    print("x is NOT present in given list")
else:
    print("x is present in given list")

if (y in list):
    print("y is present in given list")
else:
    print("y is NOT present in given list")
```

**Output**

```
x is NOT present in given list
y is present in given list
```

## 算子的优先性和结合性

[**运算符的优先级和结合性:**](https://www.geeksforgeeks.org/python-operators/) 运算符的优先级和结合性决定了运算符的优先级。

### **操作员优先**

这在具有多个不同优先级的运算符的表达式中使用，以确定首先执行哪个操作。

### 示例:运算符优先级

## 蟒蛇 3

```
# Examples of Operator Precedence

# Precedence of '+' & '*'
expr = 10 + 20 * 30
print(expr)

# Precedence of 'or' & 'and'
name = "Alex"
age = 0

if name == "Alex" or name == "John" and age >= 2:
    print("Hello! Welcome.")
else:
    print("Good Bye!!")
```

**Output**

```
610
Hello! Welcome.
```

### **操作员关联性**

如果表达式包含两个或多个具有相同优先级的运算符，则使用运算符关联性来确定。它可以是从左到右或从右到左。

### **示例:运算符**关联性

## 蟒蛇 3

```
# Examples of Operator Associativity

# Left-right associativity
# 100 / 10 * 10 is calculated as
# (100 / 10) * 10 and not
# as 100 / (10 * 10)
print(100 / 10 * 10)

# Left-right associativity
# 5 - 2 + 3 is calculated as
# (5 - 2) + 3 and not
# as 5 - (2 + 3)
print(5 - 2 + 3)

# left-right associativity
print(5 - (2 + 3))

# right-left associativity
# 2 ** 3 ** 2 is calculated as
# 2 ** (3 ** 2) and not
# as (2 ** 3) ** 2
print(2 ** 3 ** 2)
```

**Output**

```
100.0
6
0
512
```

## [Python 运算符测验](https://www.geeksforgeeks.org/operators-gq/)