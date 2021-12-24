# Python 中的三重引号

> 原文:[https://www.geeksforgeeks.org/triple-quotes-in-python/](https://www.geeksforgeeks.org/triple-quotes-in-python/)

跨多行字符串可以使用 python 的三重引号来完成。它也可以用于代码中的长注释。三重引号中还可以使用特殊字符，如制表符、逐字或换行符。顾名思义，它的语法由三个连续的单引号或双引号组成。

> **语法:**“字符串”或“‘字符串’”

**注:** 三重引号，根据 Python 官方文档是 docstring，或者多行 docstring 和**不算注释。**三重引号内的任何内容都由翻译阅读。当解释器遇到散列符号时，它会忽略其后的所有内容。这就是评论的定义。

### **多行字符串的三重引号**

## 蟒蛇 3

```py
"""This is a really long comment that can make
the code look ugly and uncomfortable to read on
a small screen so it needs to be broken into
multi-line strings using double triple-quotes"""

print("hello Geeks")
```

**Output:** 

```py
hello Geeks
```

类似地，**单引号三引号**也可以用于如下所示的相同目的:

## 蟒蛇 3

```py
'''This is a really long comment that can make
the code look ugly and uncomfortable to read on
a small screen so it needs to be broken into
multi-line strings using double triple-quotes'''

print("hello Geeks")
```

**Output:** 

```py
hello Geeks
```

**注意:**我们也可以在倍数行使用#号，但是三倍引号看起来要好得多。

### **字符串创建的三重引号**

三重引号的另一个用例是在 Python 中创建字符串。在三重引号中添加所需的字符可以将这些字符转换成 python 字符串。下面的代码显示了使用三重引号创建字符串:

**例 1:**

## 蟒蛇 3

```py
str1 = """I """
str2 = """am a """
str3 = """Geek"""

# check data type of str1, str2 & str3
print(type(str1))
print(type(str2))
print(type(str3))

print(str1 + str2 + str3)
```

**Output:** 

```py
<class 'str'>
<class 'str'>
<class 'str'>
I am a Geek
```

**示例 2:**
使用三重引号的多行字符串。默认情况下包括行尾。

## 蟒蛇 3

```py
my_str = """I
am
a
Geek !"""

# check data type of my_str
print(type(my_str))

print(my_str)
```

**Output:** 

```py
<class 'str'>
I
am
a
Geek !
```

**例 3:**
如果我们希望忽略行尾，我们需要使用”。

## 蟒蛇 3

```py
my_str = """I \
am \
a \
Geek !"""

# check data type of my_str
print(type(my_str))

print(my_str)
```

**Output:** 

```py
<class 'str'>
I am a Geek !
```