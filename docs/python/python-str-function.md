# Python str()函数

> 原文:[https://www.geeksforgeeks.org/python-str-function/](https://www.geeksforgeeks.org/python-str-function/)

**Python str()函数**返回对象的字符串版本。

> **语法:** str(对象，编码='utf-8？，错误= '严格')
> 
> **参数:**
> 
> *   **对象:**要返回字符串表示的对象。
> *   **编码:**给定对象的编码。
> *   **错误:**解码失败时的响应。
> 
> **返回:**给定对象的字符串版本

## Python str()函数示例

### **例 1:**str()函数的**演示**

## 蟒蛇 3

```py
# Python program to demonstrate
# strings

# Empty string
s = str()
print(s)

# String with values
s = str("GFG")
print(s)
```

**输出:**

```py
GFG
```

### **示例 2:** 转换为字符串

## 蟒蛇 3

```py
# Python program to demonstrate
# strings

num = 100
s = str(num)
print(s, type(s))

num = 100.1
s = str(num)
print(s, type(s))
```

**输出:**

```py
100 <class 'str'>
100.1 <class 'str'>
```

## 字符串中的错误

这个函数有六种类型的错误。

*   **严格(默认):**它会引发一个 UnicodeDecodeError。
*   **忽略:**它忽略不可编码的 Unicode
*   **替换:**用问号替换不可编码的 Unicode
*   **xmlcharfreplace:**它插入 XML 字符引用，而不是不可编码的 Unicode
*   **backlashread:**插入一个\ uNNNN Espace 序列，而不是不可编码的 Unicode
*   **namereplace:** 插入一个\N{…}转义序列，而不是不可转义的 Unicode

**示例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# str()

a = bytes("ŽString", encoding = 'utf-8')
s = str(a, encoding = "ascii", errors ="ignore")
print(s)
```

**输出:**

```py
String
```

在上面的例子中，字符**应该会产生错误，因为它不能被 ASCII 解码。但是它被忽略了，因为错误被设置为**忽略**。**