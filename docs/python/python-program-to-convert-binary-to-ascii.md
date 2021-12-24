# Python 程序将二进制转换为 ASCII

> 原文:[https://www . geesforgeks . org/python-program-to-convert-binary-to-ascii/](https://www.geeksforgeeks.org/python-program-to-convert-binary-to-ascii/)

在本文中，我们将看到 Python 编程语言中二进制到 ASCII 的转换。有多种方法可以执行这种转换，如下所示:

## **方法 1:** 使用**双星**模块

Binascii 帮助在二进制和各种 ascii 编码的二进制表示之间进行转换。

**b2a_uu()函数:**这里的“uu”代表“UNIX 到 UNIX 编码”，它负责根据指定的程序将数据从字符串转换为二进制和 ASCII 值。

**b2a_uu()** 函数用于将指定的二进制字符串转换为其对应的等效 ASCII 码。

> **语法:** b2a_uu(文本)
> 
> **参数:**该函数接受单个参数，如下图所示:
> 
> *   **文本:**这是指定的二进制字符串，将被转换为其等效的 ASCII。
> 
> **返回值:**该函数返回等效的 ASCII 码。

#### **示例:将二进制转换为 ASCII。**

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of Binary to ASCII

# Importing binascii module
import binascii

# Initializing a binary string
Text = b"GFG is a CS Portal"

# Calling the b2a_uu() function to
# Convert the binary string to ascii
Ascii = binascii.b2a_uu(Text)

# Getting the ASCII equivalent
print(Ascii)
```

**输出:**

```py
b"21T9'(&ES(&$@0U,@4&]R=&%L\n"
```

## **方法二:使用**内置类型。

这里我们将使用一个内置类型将二进制转换为 ASCII 值。

首先调用 **int(binary_sting，base)** ，以 base 为 2 表示二进制字符串。然后调用 **int.to_bytes(byte_number，byte_order)** 函数，其中 byte_order 取“大”，byte_number 取 binary_int 占用的字节数，返回字节数组。这个字节数可以通过运算**二进制 _int.bit_length() + 7 // 8 找到。**然后调用 array.decode 操作将数组变成 ASCII 文本。

#### **示例:将二进制转换为 ASCII**

## 蟒蛇 3

```py
# Python program to illustrate the
# conversion of Binary to ASCII

# Initializing a binary string in the form of
# 0 and 1, with base of 2
binary_int = int("11000010110001001100011", 2);

# Getting the byte number
byte_number = binary_int.bit_length() + 7 // 8

# Getting an array of bytes
binary_array = binary_int.to_bytes(byte_number, "big")

# Converting the array into ASCII text
ascii_text = binary_array.decode()

# Getting the ASCII value
print(ascii_text)
```

**输出:**

```py
abc
```