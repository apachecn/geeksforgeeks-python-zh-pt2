# Python 程序查找并打印变量地址

> 原文:[https://www . geesforgeks . org/python-program-to-find-print-address-of-variable/](https://www.geeksforgeeks.org/python-program-to-find-and-print-address-of-variable/)

在本文中，我们将看到如何查找和打印 Python 变量的地址。

**可以这样做:**

*   使用 id()函数
*   使用 addressof()函数
*   使用十六进制()函数

## **方法 1:** 使用 [id()](https://www.geeksforgeeks.org/id-function-python/) 查找并打印变量的地址

我们可以使用 id()函数获取地址，id()函数给出特定对象的地址。

> **语法:** id(对象)
> 
> 其中，object 是数据变量。

这里我们要找到列表、变量、元组和字典的地址。

## 蟒蛇 3

```py
# get id of list
a = [1, 2, 3, 4, 5]
print(id(a))

# get id of a variable
a = 12
print(id(a))

# get id of tuple
a = (1, 2, 3, 4, 5)
print(id(a))

# get id of a dictionary
a = {'a' : 1, 'b' : 2}
print(id(a))
```

**输出:**

```py
140234866534752
94264748411744
140234904267376
140234866093264
```

## **方法 2:** 使用 Address of()查找并打印变量的地址

我们也可以使用这些函数获取内存地址，ctypes 是 Python 的一个外来函数库。它提供 C 兼容的数据类型，并允许在 dll 或共享库中调用函数。

> **语法:** addressof(c_int(object))
> 
> 其中对象是数据变量

#### 示例:获取变量内存地址的 Python 程序。

## 蟒蛇 3

```py
# import addressof,
# c_int modules from ctypes module
from ctypes import c_int, addressof

# get memory address of variable
a = 44
print(addressof(c_int(a)))
```

**输出:**

```py
140234866278064
```

## **方法 3:** 使用[**hex()**](https://www.geeksforgeeks.org/python-hex-function/) 查找并打印变量地址

这里我们将调用 hex(地址)函数，将内存地址转换为十六进制表示。

> **语法:**十六进制(id(object))
> 
> 哪里，
> 
> *   hex()是地址的内存十六进制表示
> *   id 用于获取对象的内存
> *   对象是数据

#### **示例:** Python 程序获取内存地址的十六进制表示。

## 蟒蛇 3

```py
# get id of list in hexadecimal representation
a = [1, 2, 3, 4, 5]
print(hex(id(a)))

# get id of a variable in hexadecimal representation
a = 12
print(hex(id(a)))

# get id of tuple in hexadecimal representation
a = (1, 2, 3, 4, 5)
print(hex(id(a)))

# get id of a dictionary in hexadecimal representation
a = {'a': 1,'b' : 2}
print(hex(id(a)))
```

**输出:**

```py
0x7fba9b0ae8c0
0x5572da858b60
0x7fba9f3c4a10
0x7fba9b05b8c0
```