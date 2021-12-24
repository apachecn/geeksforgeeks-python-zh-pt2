# 美观组–使用 CSS 选择器按 CSS 类查找标签

> 原文:[https://www . geesforgeks . org/beautulsoup-find-tags-by-CSS-class-with-CSS-selecters/](https://www.geeksforgeeks.org/beautifulsoup-find-tags-by-css-class-with-css-selectors/)

**先决条件** : [美丽组合](https://www.geeksforgeeks.org/beautifulsoup-object-python-beautifulsoup/)

是一个用于网页抓取的 Python 库。美丽的输出对象由美丽的汤提供，这是一个 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。美化输出对象将解析后的文档作为一个整体来表示。这个强大的 python 工具也可以用来修改 HTML 网页。本文描述了如何使用 CSS 选择器通过 CSS 类来使用漂亮的组来查找标签。为此，使用模块的 **find_all()** 方法。

**语法:**

> find _ all(class _ =“class _ name”)
> 
> 返回具有特定 css 类的标签。

**进场:**

*   导入模块
*   从网页上删除数据。
*   解析刮到 HTML 的字符串。
*   使用 find_all()函数获取具有给定类名的标记列表。
*   打印标签。

**示例 1:** 从 HTML 文件中查找特定 CSS 类的所有标签。

## 蟒蛇 3

```
# importing module
from bs4 import BeautifulSoup

markup = """

<!DOCTYPE>
<html>
  <head><title>Example</title></head>
    <body>
        <div class="first"> Div with Class first
        </div> 
        <p class="first"> Para with Class first
        </p>

        <div class="second"> Div with Class second
        </div>
        <span class="first"> Span with Class first
        </span> 
    </body>
</html>
"""

# parsering string to HTML
soup = BeautifulSoup(markup, 'html.parser')

# printing tags with given class name
for i in soup.find_all(class_="first"):
    print(i.name)
```

**输出:**

```
div
p
span
```

**示例 2:** 从 URL 中查找特定 CSS 类的所有标签。

## 蟒蛇 3

```
# importing module
from bs4 import BeautifulSoup
import requests

URL = "https://www.geeksforgeeks.org/"
html = requests.get(URL)

# parsering string to HTML
soup = BeautifulSoup(html.content, "html5lib")

# printing tags with given class name
for i in soup.find_all(class_="article--container_content"):
    print(i.name)
```

**输出:**

```
div
```