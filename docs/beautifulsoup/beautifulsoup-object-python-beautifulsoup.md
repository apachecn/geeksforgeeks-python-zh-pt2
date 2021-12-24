# 美丽的物体 python 美丽的物体

> 原文:[https://www . geesforgeks . org/beautulsoup-object-python-beautulsoup/](https://www.geeksforgeeks.org/beautifulsoup-object-python-beautifulsoup/)

**美颜组**对象由美颜汤提供，美颜汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。美化输出对象将解析后的文档作为一个整体来表示。大多数情况下，您可以将其视为标签对象。

> **语法:**美化组(文档、解析器)
> 
> **参数:**该函数接受两个参数，解释如下:
> 
> *   **文档:**此参数包含 XML 或 HTML 文档。
> *   **解析器:**此参数包含用于解析文档的解析器的名称。

**下面给出的例子解释了《美丽的汤》中美丽的情侣对象的概念。**
**示例 1:** 在本例中，我们将创建一个包含一个美丽的输出对象的文档，并打印一个标签。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <h2> Heading 1 </h2>
        <h1> Heading 2 </h1>
    </html>
    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Print the tag
print(tag)
```

**输出:**

```
<h2> Heading 1 </h2>

```

**示例 2:** 在本例中，我们将创建一个包含一个美丽的输出对象的文档，然后使用 attrs 方法提取属性。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''

        <h2 class="hello"> Heading 1 </h2>
        <h1> Heading 2 </h1>

    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Get the attribute
attribute = tag.attrs

# Print the output
print(attribute)
```

**输出:**

```
{'class': ['hello']}

```