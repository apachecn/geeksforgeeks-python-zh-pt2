# 单引号和双引号| Python

> 原文:[https://www . geesforgeks . org/单引号和双引号-python/](https://www.geeksforgeeks.org/single-and-double-quotes-python/)

Python 字符串函数非常流行。python 中有两种表示字符串的方法。字符串用单引号或双引号括起来。根据要求，这两种方式(单引号或双引号)都是正确的。有时我们必须在同一个字符串中一起使用引号(单引号或双引号)，在这种情况下，我们交替使用单引号和双引号，以便区分它们。

**示例#1:**
检查以下示例并分析错误–

```
#Gives Error
print('It's python')

```

**解释–**
给出无效语法错误。因为“它”后面的单引号被认为是字符串的结尾，其余部分不是字符串的一部分。

可以更正为:

```
print("It's Python !")
```

**输出:**

```
It's Python!

```

**示例#2:**
如果要在 python 中打印*【with quotes】*，这不能仅用单引号(或双引号)来完成，它需要同时使用单引号和双引号。

```
# this code prints the output within quotes.
# print WithQuotes within single quotes
print("'WithQuotes'")
print("Hello 'Python'")

# print WithQuotes within single quotes
print('"WithQuotes"')
print('Hello "Python"')
```

**输出–**

```
'WithQuotes'
Hello 'Python'
"WithQuotes"
Hello "Python"

```

**结论–**
两种类型(单引号和双引号)的选择取决于程序员的选择。通常，双引号用于字符串表示，单引号用于正则表达式、dict 键或 SQL。因此单引号和双引号都描述了 python 中的字符串，但有时我们需要使用一种类型而不是另一种类型。