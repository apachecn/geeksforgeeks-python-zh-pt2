# 标记对象–Python 美化套件

> 原文:[https://www . geesforgeks . org/tag-object-python-beautulsoup/](https://www.geeksforgeeks.org/tag-object-python-beautifulsoup/)

**标签**对象由美汤提供，美汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。标签对象对应于原始文档中的一个 XML 或 HTML 标签。此外，该对象通常用于从整个 HTML 文档中提取标签。此外，靓汤不是一个 HTTP 客户端，这意味着要报废在线网站，你首先必须使用请求模块下载它们，然后将其提供给*靓汤*进行报废。此外，如果您的文档有多个具有相同名称的标签，此对象将返回第一个找到的标签。

**先决条件:** [靓汤安装](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#installing-beautiful-soup)

**语法:**

```py
Object.tag_name
```

**参数:**该函数不接受任何参数。

**下面给出的例子解释了《美丽的汤》中 Tag 对象的概念。**
**示例 1:** 在本例中，我们将仅提取 *h1* 标记元素。

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with an HTML page
soup = BeautifulSoup('''
    <html>
        <h1>a web page</h1>
    </html>
    ''', "lxml")

# Get the tag
tag = soup.h1

# Print the output
print(tag)
```

**输出:**

```py
<h1>a web page</h1>
```

**示例 2:** 在本例中，我们将只看到*强*标记元素的类型。

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with an HTML page
soup = BeautifulSoup('''
    <html>
        <strong>a web page</strong>
    </html>
    ''', "lxml")

# Get the tag
tag = soup.strong

# Print the output
print(type(tag))
```

**输出:**

```py
<class 'bs4.element.Tag'>
```

**示例 3:** 在本例中，我们将看到带有多个标签的 HTML 的输出。

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <strong>the first strong tag</strong>
        <h1> Heading </h1>
        <strong>the second strong tag</strong>
    </html>
    ''', "lxml")

# Get the tag
tag = soup.strong

# Print the output
print(tag)
```

**输出:**

```py
<strong>the first strong tag</strong>
```