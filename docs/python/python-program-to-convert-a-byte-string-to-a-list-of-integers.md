# Python 程序将一个字节串转换成一个整数列表

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-byte-string-to-list-of-integer/](https://www.geeksforgeeks.org/python-program-to-convert-a-byte-string-to-a-list-of-integers/)

给定一个字节字符串。任务是编写一个 Python 程序，将字符串的这个字节转换成整数列表。

## **方法 1:** 使用**列表()**功能

**list()** 函数用于根据作为其参数的指定 iterable 创建一个列表。

> **语法:**
> 
> 列表([可列表])
> 
> **参数:**该函数接受一个参数，如下图所示:
> 
> *   **可迭代:**这是将被创建为另一个列表的指定序列。
> 
> **返回值:**该函数返回一个新列表，该列表是根据作为参数传递的给定 iterable 创建的。

**示例:** Python 程序将一个字节串转换成一个整数列表

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of a byte string
# to a list of integers

# Initializing a byte string as GFG
x = b'GFG'

# Calling the list() function to
# create a new list of integers that  
# are the ascii values of the byte
# string GFG
print(list(x))
```

**输出:**

```py
[71, 70, 71]
```

## **方法 2:** 使用[进行循环](https://www.geeksforgeeks.org/python-for-loops/)和[命令()](https://www.geeksforgeeks.org/ord-function-python/)功能

**order()**函数用于返回代表指定字节字符的 Unicode 代码的数字。

> **语法:**
> 
> 顺序(字符)
> 
> **参数:**该函数接受单个参数，如下图所示:
> 
> *   **字符:**这是指定的字节字符串。
> 
> **返回值:**此函数返回代表指定字节字符的 Unicode 代码的数字。

**示例:** Python 程序将一个字节串转换成一个整数列表

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of a byte string
# to a list of integers

# Initializing a byte string
S = "GFG is a CS Portal"

nums = []

# Calling the for loop to iterate each
# characters of the given byte string
for chr in S:

    # Calling the ord() function
    # to convert the specified byte
    # characters to numbers of the unicode
    nums.append(ord(chr))

# Printing the unicode of the byte string
print(nums)
```

**输出:**

> [71, 70, 71, 32, 105, 115, 32, 97, 32, 67, 83, 32, 80, 111, 114, 116, 97, 108]

## **方法 3:** 使用 [from_bytes()](https://www.geeksforgeeks.org/python-bit-functions-on-int-bit_length-to_bytes-and-from_bytes/) 函数

**from_bytes()** 函数用于将指定的字节字符串转换为其对应的 int 值。

> **语法:**
> 
> int.from_bytes(字节，byteorder，*，有符号=False)
> 
> **参数:**该函数接受一些参数，如下图所示:
> 
> *   **字节:**一个字节对象
> *   **byteorder:** 此参数决定整数值的表示顺序。byteorder 的值可以是“小”，最高有效位存储在末尾，最低有效位存储在开头，也可以是“大”，MSB 存储在开头，LSB 存储在结尾。大字节顺序计算基数为 256 的整数值。
> *   **符号:**默认值为假。此参数指示是否表示数字的二进制补码。
> 
> **返回值:**这个函数返回一个与给定字节等价的 int。

**示例:** Python 程序将一个字节串转换成一个整数列表

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of a byte string
# to a list of integers

# Initializing byte value
byte_val = b'\x00\x01'

# Converting to int
# byteorder is big where MSB is at start
int_val = int.from_bytes(byte_val, "big")

# Printing int equivalent
print(int_val)
```

**输出:**

```py
1
```

**示例 2:** Python 程序将一个字节串转换成一个整数列表

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of a byte string
# to a list of integers

# Initializing a byte string
byte_val = b'\xfc\x00'

# 2's complement is enabled in big
# endian byte order format
int_val = int.from_bytes(byte_val, "big", signed="True")

# Printing int object
print(int_val)
```

**输出:**

```py
-1024
```