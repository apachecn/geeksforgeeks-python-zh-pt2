# Python RegEx

> 原文:[https://www.geeksforgeeks.org/python-regex/](https://www.geeksforgeeks.org/python-regex/)

在 Python 中，可以很容易地检查另一个字符串中是否存在文本字符串。但是，在某些情况下，我们可能没有精确的文本来匹配。例如，如果您想检查是否存在任何有效的电子邮件地址，该怎么办。这就是正则表达式发挥作用的地方。在本节中，我们将探索正则表达式并了解各种正则表达式。

*   regular expression
*   Why regular expressions
*   Basic regular expression
*   More regular expressions
*   Compile regular expression

## 正则表达式

正则表达式是基于预定义模式匹配文本的强大工具。它可以通过与特定模式匹配来检测文本的存在与否，还可以将模式拆分为一个或多个子模式。Python 标准库为正则表达式提供了 ***re 模块*** 。它的主要功能是提供一个搜索，它接受一个正则表达式和一个字符串。在这里，它要么返回第一个匹配项，要么不返回。

## python 3

```
import re

match = re.search(r'portal', 'GeeksforGeeks: A computer science \
                  portal for geeks')
print(match)
print(match.group())

print('Start Index:', match.start())
print('End Index:', match.end())
```

**输出**

```
<_sre.SRE_Match object; span=(52, 58), match='portal'>
portal
Start Index: 52
End Index: 58

```