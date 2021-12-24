# Python 中的正则表达式示例|集合 1

> 原文:[https://www . geesforgeks . org/正则表达式-python-examples-set-1/](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

A **正则表达式(RegEx)** 是一个特殊的字符序列，它使用搜索模式来查找一个字符串或一组字符串。它可以通过与特定模式匹配来检测文本的存在与否，还可以将模式拆分为一个或多个子模式。Python 提供了一个支持在 Python 中使用正则表达式的 **re** 模块。它的主要功能是提供一个搜索，它接受一个正则表达式和一个字符串。在这里，它要么返回第一个匹配项，要么不返回。

**例:**

## 蟒 3

```py
import re

s = 'GeeksforGeeks: A computer science portal for geeks'

match = re.search(r'portal', s)

print('Start Index:', match.start())
print('End Index:', match.end())
```

**输出**

```py
Start Index: 34
End Index: 40
```