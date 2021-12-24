# Python 字符串|可打印()

> 原文:[https://www.geeksforgeeks.org/python-string-printable/](https://www.geeksforgeeks.org/python-string-printable/)

在 Python3 中， **`string.printable`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.printable`将给出所有的标点符号、数字、ascii 字母和空白。

> **语法:**字符串。可打印
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回所有标点、数字、ascii _ 字母和空格的集合。

**注意:**确保导入字符串库函数以便使用字符串。可打印

**代码#1 :**

```
# import string library function 
import string 

# Storing the sets of punctuation,
# digits, ascii_letters and whitespace
# in variable result 
result = string.printable

# Printing the set of values 
print(result) 
```

**输出:**

```
0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&'()*+, -./:;<=>?@[\]^_`{|}~ 

```

**代码#2 :** 给出可打印值的代码测试。

```
# import string library function 
import string 

# An input string.
Sentence = "Hey, Geeks !, How are you?"

for i in Sentence:

    # checking whether the char is printable value
    if i in string.printable:

        # Printing the printable values 
        print("printable Value is: " + i)
```

**输出:**

```
printable Value is: H
printable Value is: e
printable Value is: y
printable Value is:,
printable Value is:  
printable Value is: G
printable Value is: e
printable Value is: e
printable Value is: k
printable Value is: s
printable Value is: !
printable Value is:,
printable Value is:  
printable Value is: H
printable Value is: o
printable Value is: w
printable Value is:  
printable Value is: a
printable Value is: r
printable Value is: e
printable Value is:  
printable Value is: y
printable Value is: o
printable Value is: u
printable Value is: ?

```