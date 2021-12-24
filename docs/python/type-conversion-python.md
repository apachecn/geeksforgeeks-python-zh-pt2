# Python 中的类型转换

> 原文:[https://www.geeksforgeeks.org/type-conversion-python/](https://www.geeksforgeeks.org/type-conversion-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型，这在日常和竞争性编程中非常有用。本文旨在提供关于某些转换函数的信息。

Python 中有两种类型的类型转换:

1.  隐式类型转换
2.  显式类型转换

让我们详细讨论一下。

## 隐式类型转换

在 Python 中数据类型的隐式类型转换中，Python 解释器会自动将一种数据类型转换为另一种数据类型，而无需任何用户参与。为了更清楚地了解这个主题，请看下面的例子。

**示例:**

## 蟒蛇 3

```py
x = 10

print("x is of type:",type(x))

y = 10.6
print("y is of type:",type(y))

x = x + y

print(x)
print("x is of type:",type(x))
```

**输出:**

```py
x is of type: <class 'int'>
y is of type: <class 'float'>
20.6
x is of type: <class 'float'>
```

正如我们所看到的,“x”的类型从“整数”类型自动变成了“浮点”类型。这是 python 中隐式类型转换的一个简单案例。

## 显式类型转换

在 Python 的显式类型转换中，数据类型由用户根据自己的要求手动更改。显式类型转换的各种形式解释如下:

**1。int(a，** **base)** :该函数将**任意数据类型转换为整数**。“Base”指定**的基数，如果数据类型是字符串，则字符串为**。
**2。float()** :该功能用于将**任意数据类型转换为**浮点**数**

## 蟒蛇 3

```py
# Python code to demonstrate Type conversion
# using int(), float()

# initializing string
s = "10010"

# printing string converting to int base 2
c = int(s,2)
print ("After converting to integer base 2 : ", end="")
print (c)

# printing string converting to float
e = float(s)
print ("After converting to float : ", end="")
print (e)
```

**输出:**

```py
After converting to integer base 2 : 18
After converting to float : 10010.0
```

**3。order():**该函数用于将**字符转换为整数。**
**4。hex() :** 该功能是将**整数转换为十六进制字符串**。
**5。oct() :** 该功能是将**整数转换为八进制字符串**。

## 蟒蛇 3

```py
# Python code to demonstrate Type conversion
# using  ord(), hex(), oct()

# initializing integer
s = '4'

# printing character converting to integer
c = ord(s)
print ("After converting character to integer : ",end="")
print (c)

# printing integer converting to hexadecimal string
c = hex(56)
print ("After converting 56 to hexadecimal string : ",end="")
print (c)

# printing integer converting to octal string
c = oct(56)
print ("After converting 56 to octal string : ",end="")
print (c)
```

**输出:**

```py
After converting character to integer : 52
After converting 56 to hexadecimal string : 0x38
After converting 56 to octal string : 0o70
```

**6。tuple() :** 这个函数用来**转换成 tuple** 。
**7。set() :** 该功能转换为 set 后返回**类型。
**8。list() :** 该功能用于将**任意数据类型转换为列表类型**。**

## 蟒蛇 3

```py
# Python code to demonstrate Type conversion
# using  tuple(), set(), list()

# initializing string
s = 'geeks'

# printing string converting to tuple
c = tuple(s)
print ("After converting string to tuple : ",end="")
print (c)

# printing string converting to set
c = set(s)
print ("After converting string to set : ",end="")
print (c)

# printing string converting to list
c = list(s)
print ("After converting string to list : ",end="")
print (c)
```

**输出:**

```py
After converting string to tuple : ('g', 'e', 'e', 'k', 's')
After converting string to set : {'k', 'e', 's', 'g'}
After converting string to list : ['g', 'e', 'e', 'k', 's']
```

**9。dict() :** 这个函数用来**将一个元组的顺序(键，值)转换成字典**。
**10。str() :** 用于**将整数转换为字符串。**
**11。复数(实数，imag) :** 此功能**将实数转换为复数(实数，imag)。**

## 蟒蛇 3

```py
# Python code to demonstrate Type conversion
# using  dict(), complex(), str()

# initializing integers
a = 1
b = 2

# initializing tuple
tup = (('a', 1) ,('f', 2), ('g', 3))

# printing integer converting to complex number
c = complex(1,2)
print ("After converting integer to complex number : ",end="")
print (c)

# printing integer converting to string
c = str(a)
print ("After converting integer to string : ",end="")
print (c)

# printing tuple converting to expression dictionary
c = dict(tup)
print ("After converting tuple to dictionary : ",end="")
print (c)
```

**输出:**

```py
After converting integer to complex number : (1+2j)
After converting integer to string : 1
After converting tuple to dictionary : {'a': 1, 'f': 2, 'g': 3}
```

**12 时。chr(数字):**此功能**将数字转换为其对应的 ASCII 字符。**

## 蟒蛇 3

```py
# Convert ASCII value to characters
a = chr(76)
b = chr(77)

print(a)
print(b)
```

**输出:**

```py
L
M

```

本文由**曼吉特·辛格(S. Nandini)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。