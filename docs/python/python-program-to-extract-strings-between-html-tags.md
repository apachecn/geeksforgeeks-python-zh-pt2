# Python 程序提取 HTML 标签之间的字符串

> 原文:[https://www . geesforgeks . org/python-程序-提取-字符串-html-tags/](https://www.geeksforgeeks.org/python-program-to-extract-strings-between-html-tags/)

给定一个字符串和 HTML 标记，提取指定标记之间的所有字符串。

> **输入** : ' < b > Gfg < /b >为< b >最佳< /b >。我喜欢从里面读<b>CS</b>，tag = "br"
> **输出** : ['Gfg '，' Best '，' Reading CS']
> **解释**:提取“br”标签之间的所有字符串。
> 
> **输入**:'<h1>Gfg</h1>为< h1 > Best < /h1 >我爱罗<h1>Reading CS</h1>'，tag =“h1”
> **输出【T4:【‘Gfg’，‘Best’，‘Reading CS’】
> **解释**:所有“h1”tag 之间的字符串都被提取出来。**

使用 **re 模块**可以执行该任务。在本例中，我们使用， [findall()](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/#:~:text=findall()%20%3A%20Return%20all%20non,(Source%20%3A%20Python%20Docs).) 函数，通过匹配使用标记和符号构建的适当正则表达式来提取所有字符串。

## 蟒蛇 3

```py
# importing re module
import re

# initializing string
test_str = '<b>Gfg</b> is <b>Best</b>. I love <b>Reading CS</b> from it.'

# printing original string
print("The original string is : " + str(test_str))

# initializing tag
tag = "b"

# regex to extract required strings
reg_str = "<" + tag + ">(.*?)</" + tag + ">"
res = re.findall(reg_str, test_str)

# printing result
print("The Strings extracted : " + str(res))
```

**输出:**

> 原弦为: **Gfg** 为 **Best** 。我喜欢从里面阅读**CS**。
> 提取的字符串:['Gfg '，' Best '，' Reading CS']