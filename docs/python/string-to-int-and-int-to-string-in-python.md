# Python 中的字符串到 Int 和 Int 到字符串

> 原文:[https://www . geesforgeks . org/python 中的字符串到 int 和 int 到字符串/](https://www.geeksforgeeks.org/string-to-int-and-int-to-string-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型。本文旨在提供关于将字符串转换为 int 和将 int 转换为 string 的信息。

## 将字符串转换为 int

如果我们想将字符串中表示的数字转换为 int，我们必须使用 **int()** 函数。该功能用于将给定基数的数字转换为十进制。

> **语法:** int(字符串，基数)
> 
> **参数:**
> 
> **字符串:**由 1 和 0 组成
> 
> **基数:**(整数值)数字的基数。

**示例:**

## 蟒蛇 3

```
# string data
n = '321'
print('Type of num is :', type(n))

# convert using int()
n = int(n)
print('So Now, type of num is :', type(n))
```

**输出:**

```
Type of num is : <class 'str'>
So Now, type of num is : <class 'int'>
```

## 将 Int 转换为字符串

使用 str()函数可以将 int 数据类型转换为 string。

> **语法:**字符串(对象，编码='utf-8 '，错误='strict ')
> 
> **参数:**
> 
> **对象:**要返回字符串表示的对象。
> 
> **编码:**给定对象的编码。
> 
> **错误:**解码失败时的响应。

**示例:**

## 蟒蛇 3

```
hdv = 0x1eff
print('Type of hdv :', type(hdv))

# Converting to string
hdv = str(hdv)
print('Type of hdv now :', type(hdv))
```

**输出:**

```
Type of hdv : <class 'int'>
Type of hdv now : <class 'str'>
```