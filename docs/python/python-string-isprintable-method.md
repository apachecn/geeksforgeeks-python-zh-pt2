# Python 字符串可打印()方法

> 原文:[https://www . geesforgeks . org/python-string-is printable-method/](https://www.geeksforgeeks.org/python-string-isprintable-method/)

Python String isprintable()是一种用于字符串处理的内置方法。如果字符串中的所有字符都是可打印的或字符串为空，isprintable()方法返回“真”，否则返回“假”。此函数用于检查参数是否包含任何可打印字符，例如:

*   数字(0123456789)
*   大写字母(ABCDEFGHIJKLMNOPQRSTUVWXYZ)
*   小写字母(abcdefghijklmnopqrstuvwxyz)
*   标点符号(！"#$%&'()*+, -./:;？@[\]^_`{ | }~ )
*   空间( )

> **语法:**
> 
> string.isprintable()
> 
> **参数:**
> 
> isprintable()不接受任何参数
> 
> **返回:**
> 
> *   如果字符串中的所有字符都是可打印的或字符串为空，则为 True。
> *   false–如果字符串包含 1 个或更多不可打印的字符。
> 
> **错误或异常:**
> 
> 1.  该函数不接受任何参数，因此不应传递任何参数，否则将返回错误。
> 2.  唯一可打印的空白字符是*空格*或“”，否则每个空白字符都不可打印，函数返回“假”。
> 3.  空字符串被认为是可打印的，它返回“真”。

### 例 1

```
Input : string = 'My name is Ayush'
Output : True

Input : string = 'My name is \n Ayush'
Output : False

Input : string = ''
Output : True
```

## 蟒蛇 3

```
# Python code for implementation of isprintable()

# checking for printable characters
string = 'My name is Ayush'
print(string.isprintable())

# checking if \n is a printable character
string = 'My name is \n Ayush'
print(string.isprintable())

# checking if space is a printable character
string = ''
print( string.isprintable())
```

**输出:**

```
True
False
True
```

### 示例 2:实用**应用**

在 python 中给定一个字符串，计算该字符串中不可打印的字符数，并用空格替换不可打印的字符。

```
Input : string = 'My name is Ayush'
Output : 0
         My name is Ayush

Input : string = 'My\nname\nis\nAyush'
Output : 3
         My name is Ayush
```

**算法:**

1.  初始化一个空的新字符串，变量计数= 0。
2.  逐个字符遍历给定的字符串直到其长度，检查该字符是否是不可打印的字符。
3.  如果是不可打印的字符，则将计数器增加 1，并在新字符串中添加一个空格。
4.  否则，如果它是一个可打印字符，按原样将其添加到新字符串中。
5.  打印计数器的值和新字符串。

## 蟒蛇 3

```
# Python implementation to count 
# non-printable characters in a string

# Given string and new string
string ='GeeksforGeeks\nname\nis\nCS portal'
newstring = ''

# Initialising the counter to 0
count = 0

# Iterating the string and 
# checking for non-printable characters
# Incrementing the counter if a 
# non-printable character is found 
# and replacing it by space in the newstring

# Finally printing the count and newstring

for a in string:
    if (a.isprintable()) == False:
            count+= 1
            newstring+=' '
    else:
            newstring+= a
print(count)
print(newstring)
```

**输出:**

```
3
GeeksforGeeks name is CS portal
```