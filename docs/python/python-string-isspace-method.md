# Python 字符串 isspace()方法

> 原文:[https://www.geeksforgeeks.org/python-string-isspace-method/](https://www.geeksforgeeks.org/python-string-isspace-method/)

Python String **isspace()** 是一种用于字符串处理的内置方法。如果字符串中的所有字符都是空白字符，isspace()方法返回“真”，否则返回“假”。此函数用于检查参数是否包含所有空白字符，例如:

*   “–空间
*   \ '–水平选项卡
*   \ n '–换行符
*   \ v '–垂直标签
*   \ f '–提要
*   \ r '–回车

> **语法:**
> 
> string.isspace()
> 
> **参数:**
> 
> isspace()不接受任何参数
> 
> **返回:**
> 
> 1.  **真**–如果字符串中的所有字符都是空白字符。
> 2.  **False**–如果字符串包含 1 个或多个非空白字符。

### **例 1**

```py
Input : string = 'Geeksforgeeks'
Output : False

Input : string = '\n \n \n'
Output : True

Input : string = 'Geeks\nFor\nGeeks'
Output : False
```

## 蟒蛇 3

```py
# Python code for implementation of isspace()

# checking for whitespace characters
string = 'Geeksforgeeks'

print(string.isspace())

# checking if \n is a whitespace character
string = '\n \n \n'

print(string.isspace())

string = 'Geeks\nfor\ngeeks'
print( string.isspace())
```

**输出:**

```py
False
True
False
```

### 示例 2:实用**应用**

给定 python 中的一个字符串，计算该字符串中空白字符的数量。

```py
Input : string = 'My name is Ayush'
Output : 3

Input : string = 'My name is \n\n\n\n\nAyush'
Output : 8
```

**算法:**

1.  逐个字符遍历给定的字符串直到其长度，检查该字符是否为空白字符。
2.  如果它是一个空白字符，将计数器加 1，否则遍历到下一个字符。
3.  打印计数器的值。

## 蟒蛇 3

```py
# Python implementation to count whitespace characters in a string
# Given string
# Initialising the counter to 0
string = 'My name is Ayush'
count=0

# Iterating the string and checking for whitespace characters
# Incrementing the counter if a whitespace character is found
# Finally printing the count
for a in string:
    if (a.isspace()) == True:
        count+=1
print(count)

string = 'My name is \n\n\n\n\nAyush'
count = 0
for a in string:
    if (a.isspace()) == True:
        count+=1
print(count)
```

**输出:**

```py
3
8
```