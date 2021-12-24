# 内存中 Python 对象的意外大小

> 原文:[https://www . geeksforgeeks . org/意外大小的 python 内存对象/](https://www.geeksforgeeks.org/unexpected-size-of-python-objects-in-memory/)

在本文中，我们将讨论内存中 python 对象的意外大小。

Python 对象包括列表、元组、字典等，它们有不同的内存大小，并且每个对象都有不同的内存地址。意外大小是指我们无法预料的内存大小。但是我们可以通过 getsizeof()函数得到大小。这将返回 python 对象的内存大小。这个功能在 [sys 模块](https://www.geeksforgeeks.org/python-sys-module/)中有，所以我们需要导入。

**语法**:

```py
sys.getsizeof(object)
```

### 示例 1:获取字符串对象意外大小的 Python 代码

单个字符的字符串将消耗 50 个字节，然后在 1 个字符之后，它将消耗 n 个字符字节。

**示例:**

> ' e '将消耗–50
> 
> “eo”将消耗–51
> 
> eoo '将消耗–52

## 蟒蛇 3

```py
# import sys module
import sys

# get the size of the given string
print(sys.getsizeof('g'))

# get the size of the given string
print(sys.getsizeof('ge'))

# get the size of the given string
print(sys.getsizeof('gee'))

# get the size of the given string
print(sys.getsizeof('geek'))

# get the size of the given string
print(sys.getsizeof('geeks'))
```

**输出**:

```py
50
51
52
53
54
```

### 示例 2: Python 程序获取整数对象的意外大小

整数对象将占用 28 个字节

## 蟒蛇 3

```py
# import sys module
import sys

# get the size of the given integer
print(sys.getsizeof(123))

# get the size of the given integer
print(sys.getsizeof(21))
```

**输出:**

```py
28
28
```

### **示例 3:** 获取列表对象意外大小的 Python 代码

我们可以将列表定义为[]。空列表将消耗 72 个字节，并且每个元素消耗额外的 8 个字节。

> [] – 72
> 
> [1] – 72 + 8 = 80
> 
> [1,2] – 72 +8 + 8 =88

## 蟒蛇 3

```py
# import sys module
import sys

# get the size of empty list
print(sys.getsizeof([]))

# get the size of list with one element
print(sys.getsizeof([2]))

# get the size of list with two elements
print(sys.getsizeof([22, 33]))
```

**输出**:

```py
72
80
88
```

### 示例 4:获取意外的字典对象大小

这个对象将消耗 248 字节，与项目数无关。

## 蟒蛇 3

```py
# import sys module
import sys

# get the size of empty dictionary
print(sys.getsizeof({}))

# get the size of dictionarydictionary with one element
print(sys.getsizeof({'k': 2}))

# get the size of list with two elements
print(sys.getsizeof({'k': 2, 'h': 45}))
```

**输出**:

```py
248
248
248
```