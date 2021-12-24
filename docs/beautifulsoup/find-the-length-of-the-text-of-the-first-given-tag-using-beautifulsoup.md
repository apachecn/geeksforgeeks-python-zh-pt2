# 使用 beautulsup

找到第一个给定标签的文本长度

> 原文:[https://www . geeksforgeeks . org/find-第一个给定标签的文本长度-使用-美化组/](https://www.geeksforgeeks.org/find-the-length-of-the-text-of-the-first-given-tag-using-beautifulsoup/)

在本文中，我们将使用“美丽组”来查找第一个给定标签的文本长度。

让我们看一个示例。使用“html.parser”对其进行解析，并在下面的代码中计算标记值“h2”的长度*shoot = beautulsoup(html _ doc，‘HTML . parser’)*指定使用*HTML . parser .*The*shoot . find(‘H2’)解析整个给定的 HTML 文档。text* 方法获取任何存在于给定文档内部的有效 HTML 标签，并对其进行搜索。如果标签存在，它将完成下一组操作。如果指定的标记不存在，它将抛出“属性错误”

在这里的例子中，我们关心计算长度，因此使用了 *len()* 函数。 *len()* 函数返回对象中的项数，如果是字符串，则返回该字符串中包含的字符数。

**例 1:**

在这个例子中，我们试图得到一个出现在“h2”中的文本值，它只是计算包含在该字符串中的字符数。

## 蟒 3

```py
# import module
from bs4 import BeautifulSoup

# assign HTML document
html_doc = """
<html>

<head>
<meta http-equiv="Content-Type" content="text/html;
charset=iso-8859-1">
<title>An example of HTML page to find the length of
the first tag</title>
</head>

<body>
<h2>An example of HTML page to find the length of the
first tag</h2>

<p>
Beautiful Soup is a library which is essential to scrape
information from web pages.
It helps to iterate, search and modifying the parse tree.</p>

</body>
</html>
"""

# create beautiful soap object
soup = BeautifulSoup(html_doc, 'html.parser')

# get length
print("Length of the text of the first <h2> tag:")
print(len(soup.find('h2').text))
```

**输出:**

```py
Length of the text of the first <h2> tag:
59
```

*汤圆()。text* 语句检索包含在特定标签之间的文本。然后 *len()* 函数返回文本的长度。

**例 2 :**

获取给定 HTML 中存在的所有 HTML 标记的长度。

## 蟒 3

```py
# import module
from bs4 import BeautifulSoup

# assign html document
html_doc = """
<html>

<head>
<meta http-equiv="Content-Type" content="text/html;
charset=iso-8859-1">
<title>An example of HTML page to find the length of
the first tag</title>
</head>

<body>
<h2>An example of HTML page to find the length of the
first tag</h2>

<p>
Beautiful Soup is a library which is essential to scrape
information from web pages.
It helps to iterate, search and modifying the parse tree.</p>

</body>
</html>
"""

# create beautiful sopa object
soup = BeautifulSoup(html_doc, 'html.parser')

# Get all the tags present in the html and
# getting their length
for tag in soup.findAll(True):
    print(tag.name, " : ", len(soup.find(tag.name).text))
```