# Python |集合 2(变量、表达式、条件和函数)

> 原文:[https://www . geesforgeks . org/python-set-2-变量-表达式-条件和函数/](https://www.geeksforgeeks.org/python-set-2-variables-expressions-conditions-and-functions/)

关于 Python 的介绍已经在[这篇文章](https://www.geeksforgeeks.org/python-the-new-generation-language/)中讨论过了。现在，让我们从学习 python 开始。

**用 Python 运行你的第一个代码**
Python 程序不是被编译的，而是被解释的。现在，让我们开始编写 python 代码并运行它。请确保 python 安装在您正在使用的系统上。如果没有安装，可以从[这里](https://www.python.org/downloads/release/python-2711/)下载。我们将使用 python 2.7。

**制作 Python 文件:**
Python 文件以扩展名保存”。py”。打开一个文本编辑器，保存一个名为“hello.py”的文件。打开它并编写以下代码:

## 计算机编程语言

```py
print "Hello World"
# Notice that NO semi-colon is to be used
```

**读取文件内容:**
Linux 系统–使用“cd”命令从存储创建的文件(hello.py)的终端移动到目录，然后在终端中键入以下内容:

```py
python hello.py
```

Windows 系统–打开命令提示符，使用“cd”命令移动到存储文件的目录，然后通过将文件名写入命令来运行文件。

**Python 中的变量**
变量不需要先在 Python 中声明。它们可以直接使用。python 中的变量和大多数其他编程语言一样区分大小写。

示例:

## 计算机编程语言

```py
a = 3
A = 4
print a
print A
```

输出结果是:

```py
3
4
```

**Python 中的表达式**
Python 中的算术运算可以通过使用算术运算符和一些内置函数来执行。

## 计算机编程语言

```py
a = 2
b = 3
c = a + b
print c
d = a * b
print d
```

输出结果是:

```py
5
6
```

**Python 中的条件**
Python 中的条件输出可以通过使用 if-else 和 elif (else if)语句获得。

## 计算机编程语言

```py
a = 3
b = 9
if b % a == 0 :
    print "b is divisible by a"
elif b + 1 == 10:
    print "Increment in b produces 10"
else:
    print "You are in else statement"
```

输出结果是:

```py
b is divisible by a
```

**Python 中的函数**
Python 中的函数由函数名称前的关键字‘def’声明。函数的返回类型不需要在 python 中明确指定。可以通过在括号中写函数名后跟参数列表来调用该函数。

## 计算机编程语言

```py
# Function for checking the divisibility
# Notice the indentation after function declaration
# and if and else statements
def checkDivisibility(a, b):
    if a % b == 0 :
        print "a is divisible by b"
    else:
        print "a is not divisible by b"
#Driver program to test the above function
checkDivisibility(4, 2)
```

输出结果是:

```py
a is divisible by b
```

因此，python 是一种非常简化且编写起来不那么麻烦的语言。python 的简单性本身就促进了它的广泛使用。

*   下一篇文章- [Python 数据类型](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)
*   [测验](https://www.geeksforgeeks.org/functions-python-gq/)–Python 中的函数

本文由尼克希尔·库马尔·辛格撰写。如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。