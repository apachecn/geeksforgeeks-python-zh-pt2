# Python 中转义字符的打印方式

> 原文:[https://www . geesforgeks . org/way-print-escape-characters-python/](https://www.geeksforgeeks.org/ways-print-escape-characters-python/)

转义字符是通常用于执行某些任务的字符，它们在代码中的使用指示编译器采取映射到该字符的适当操作。

示例:

```
'\n'  -->  Leaves a line
'\t'  -->  Leaves a space 

```

```
# Python code to demonstrate escape character
# string 

ch = "I\nLove\tGeeksforgeeks"

print ("The string after resolving escape character is : ")
print (ch)
```

输出:

```
The string after resolving escape character is : 
I
Love    Geeksforgeeks

```

但是在某些情况下，希望不要解析转义，即整个未解析的字符串都有
要打印。这些是通过以下方式实现的。

**Using repr()**

该函数以可打印格式返回一个字符串，即不解析转义序列。

```
# Python code to demonstrate printing 
# escape characters from repr()

# initializing target string 
ch = "I\nLove\tGeeksforgeeks"

print ("The string without repr() is : ")
print (ch)

print ("\r")

print ("The string after using repr() is : ")
print (repr(ch))
```

输出:

```
The string without repr() is : 
I
Love    Geeksforgeeks

The string after using repr() is : 
'I\nLove\tGeeksforgeeks'

```

**Using “r/R”**

向目标字符串添加“R”或“R”会在内部触发对字符串的 repr()，并停止解析转义字符。

```
# Python code to demonstrate printing 
# escape characters from "r" or "R"

# initializing target string 
ch = "I\nLove\tGeeksforgeeks"

print ("The string without r / R is : ")
print (ch)

print ("\r")

# using "r" to prevent resolution
ch1 = r"I\nLove\tGeeksforgeeks"

print ("The string after using r is : ")
print (ch1)

print ("\r")

# using "R" to prevent resolution
ch2 = R"I\nLove\tGeeksforgeeks"

print ("The string after using R is : ")
print (ch2)
```

输出:

```
The string without r/R is : 
I
Love    Geeksforgeeks

The string after using r is : 
I\nLove\tGeeksforgeeks

The string after using R is : 
I\nLove\tGeeksforgeeks

```