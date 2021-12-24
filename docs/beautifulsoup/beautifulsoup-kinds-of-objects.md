# 美丽的组合–物体种类

> 原文:[https://www . geesforgeks . org/beautulsoup-of-objects/](https://www.geeksforgeeks.org/beautifulsoup-kinds-of-objects/)

**先决条件:** [美丽组](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

在这篇文章中，我们将讨论美丽汤里不同类型的物体。当字符串或 HTML 文档在美化组的构造函数中给出时，这个构造函数将这个文档转换成不同的 python 对象。

**四大重要对象为:**

1.  美丽的组合
2.  标签
3.  导航字符串
4.  评论

**1。** [**【美化输出对象:**](https://www.geeksforgeeks.org/beautifulsoup-object-python-beautifulsoup/) 美化输出对象代表整个解析后的文档。所以，这是我们正在努力搜集的完整文件。大多数情况下，您可以将其视为标签对象。

## 蟒 3

```py
# importing the module
from bs4 import BeautifulSoup

# parsing the document
soup = BeautifulSoup('''<h1>Geeks for Geeks</h1>''',
                     "html.parser")

print(type(soup))
```

**输出:**

```py
<class 'bs4.BeautifulSoup'>
```

**2。** [**标签对象:**](https://www.geeksforgeeks.org/tag-object-python-beautifulsoup/) 标签对象对应于原始文档中的一个 XML 或 HTML 标签。此外，该对象通常用于从整个 HTML 文档中提取标签。此外，美丽的汤不是一个 HTTP 客户端，这意味着要报废在线网站，您首先必须使用请求模块下载它们，然后将它们提供给美丽的汤进行报废。此外，如果您的文档有多个同名标签，此对象将返回第一个找到的标签。

## 蟒 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with an HTML page
soup = BeautifulSoup('''
    <html>
        <b>Geeks for Geeks</b>
    </html>
    ''', "html.parser")

# Get the tag
tag = soup.b

# Print the output
print(type(tag))
```

**输出:**

```py
<class 'bs4.element.Tag'>
```

标签包含许多方法和属性。标签的两个重要特征是它的名称和属性。

*   name
*   attribute

**#名称:**

标签的名称可以通过“”访问。' name '作为后缀。

> **语法:**tag . name
> 
> **Return:**它是标签的类型。

我们还可以更改标签的名称。

## 蟒 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with an HTML page
soup = BeautifulSoup('''
    <html>
        <b>Geeks for Geeks</b>
    </html>
    ''', "html.parser")

# Get the tag
tag = soup.b

# Print the output
print(tag.name)

# changing the tag
tag.name = "Strong"
print(tag)
```

**输出:**

```py
b
<Strong>Geeks for Geeks</Strong>
```

**#属性:**

**例 1:** 任何不是标签的东西，基本上都是属性，必须包含值。标记对象可以有许多属性，可以通过访问键或直接通过值来访问。我们还可以修改属性及其值。

## 蟒 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with an HTML page
soup = BeautifulSoup('''
    <html>
        <b class="gfg">Geeks for Geeks</b>
    </html>
    ''', "html.parser")

# Get the tag
tag = soup.b

print(tag["class"])

# modifying class
tag["class"] = "geeks"
print(tag)

# delete the class attributes
del tag["class"]
print(tag)
```