# Python 中的字符串.空白

> 原文:[https://www.geeksforgeeks.org/string-whitespace-in-python/](https://www.geeksforgeeks.org/string-whitespace-in-python/)

在 Python3 中， **`string.whitespace`** 是一个预初始化的字符串，用作字符串常量。在 Python 中，`string.whitespace`将赋予字符空格、制表符、换行符、回车符、换行符和垂直制表符。

> **语法:**字符串。空白
> 
> **参数:**不取任何参数，因为它不是函数。
> 
> **返回:**返回字符空格、制表符、换行符、回车符、换行符和垂直制表符。

**注意:**确保导入字符串库函数以便使用字符串。空白

**代码#1 :**

```py
# import string library function 
import string 

print("Hello")
# Storing the characters space, tab etc
result = string.whitespace

# Printing the values
print(result)
print("Geeksforgeeks")
```

**Output:**

```py
Hello

Geeksforgeeks

```

**代码#2 :** 给定空白值的代码测试。

```py
# import string library function 
import string 

# An input string.
Sentence = "Hey, Geeks !, How are you?"

for i in Sentence:

    # checking whether the whitespace is present 
    if i in string.whitespace:

        # Printing the whitespace values 
        print("printable Value is: " + i)
```

**Output:**

```py
printable Value is:  
printable Value is:  
printable Value is:  
printable Value is:  
printable Value is:

```