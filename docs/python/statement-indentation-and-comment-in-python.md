# Python 中的语句、缩进和注释

> 原文:[https://www . geesforgeks . org/语句-python 中的缩进和注释/](https://www.geeksforgeeks.org/statement-indentation-and-comment-in-python/)

#### 声明

在源代码中编写的用于执行的指令称为语句。Python 编程语言中有不同类型的语句，如赋值语句、条件语句、循环语句等。这些都有助于用户获得所需的输出。例如，n = 50 是赋值语句。
**多行语句:**Python 中的语句可以使用括号()、大括号{}、方括号[]、分号(；)，延续字符斜杠(\)。当程序员需要进行长时间的计算，并且无法将语句放入一行时，可以使用这些字符。
**例:**

```py
Declared using Continuation Character (\):
s = 1 + 2 + 3 + \
    4 + 5 + 6 + \
    7 + 8 + 9

Declared using parentheses () :
n = (1 * 2 * 3 + 7 + 8 + 9)

Declared using square brackets [] :
footballer = ['MESSI',
          'NEYMAR',
          'SUAREZ']

Declared using braces {} :
x = {1 + 2 + 3 + 4 + 5 + 6 +
     7 + 8 + 9}

Declared using semicolons(;) :
flag = 2; ropes = 3; pole = 4
```

#### 刻痕

块是所有这些语句的组合。块可以看作是为了特定目的的语句分组。大多数编程语言，如 C、C++、Java，都使用大括号{ }来定义一段代码。Python 的一个显著特点是它使用缩进来突出代码块。空白在 Python 中用于缩进。右边距离相同的所有语句都属于同一个代码块。如果一个块必须嵌套得更深，它只需进一步向右缩进。看下面几行代码可以更好理解:

## 蟒蛇 3

```py
# Python program showing
# indentation

site = 'gfg'

if site == 'gfg':
    print('Logging on to geeksforgeeks...')
else:
    print('retype the URL.')
print('All set !')
```

**输出:**

```py
Logging on to geeksforgeeks...
All set !
```

行打印('登录极客网站…')和打印('重新输入网址')是两个独立的代码块。我们的 if 语句示例中的两个代码块都缩进了四个空格。最后的印刷(‘全部准备好了！’)不缩进，因此它不属于 else-block。

## 蟒蛇 3

```py
j = 1
while(j<= 5):
     print(j)
     j = j + 1
```

**输出:**

```py
1
2
3
4
5
```

要在 Python 中表示一个代码块，必须用相同的空格缩进代码块的每一行。while 循环中的两行代码都缩进了四个空格。它是指示语句属于哪个代码块所必需的。例如，j=1 和 while(j <=5): is not indented, and so it is not within the while block. So, Python code structures by indentation.

#### 评论

Python 开发人员经常使用注释系统，因为如果不使用它，事情会变得非常混乱，非常快。注释是开发人员提供的有用信息，可以让读者理解源代码。它解释了代码中使用的逻辑或部分逻辑。当你不再回答关于代码的问题时，注释通常对维护或增强代码的人很有帮助。这些经常被引用为一种有用的编程惯例，它不参与程序的输出，但是提高了整个程序的可读性。Python 中有两种类型的注释:
**单行注释:** Python 单行注释以没有空格(#)的 hashtag 符号开始，一直持续到行尾。如果注释超过一行，那么在下一行放一个标签并继续注释。Python 的单行注释对于提供变量、函数声明和表达式的简短解释非常有用。参见下面演示单行注释的代码片段:
**代码 1:**

## 蟒蛇 3

```py
# This is a comment
# Print “GeeksforGeeks !” to console
print("GeeksforGeeks")
```

**代码 2:**

## 蟒蛇 3

```py
a, b = 1, 3 # Declaring two integers
sum = a + b # adding two integers
print(sum) # displaying the output
```

**多行字符串作为** **注释:** Python 多行注释是一段包含在注释两端的分隔符(“”)中的文本。同样，分隔符(“”)之间不应有空格。当注释文本不适合一行时，它们很有用；因此需要跨线。多行注释或段落作为其他人阅读您的代码的文档。参见以下演示多行注释的代码片段:
**代码 1:**

## 蟒蛇 3

```py
"""
This would be a multiline comment in Python that
spans several lines and describes geeksforgeeks.
A Computer Science portal for geeks. It contains
well written, well thought
and well-explained computer science
and programming articles,
quizzes and more.
…
"""
print("GeeksForGeeks")
```

**代码 2:**

## 蟒蛇 3

```py
'''This article on geeksforgeeks gives you a
perfect example of
multi-line comments'''

print("GeeksForGeeks")
```