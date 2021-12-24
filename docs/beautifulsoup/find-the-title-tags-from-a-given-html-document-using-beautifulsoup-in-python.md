# 使用 Python 中的美化程序从给定的 html 文档中找到标题标签

> 原文:[https://www . geeksforgeeks . org/find-the-title-tags-from-a-给定-html-document-using-beauty-oup-in-python/](https://www.geeksforgeeks.org/find-the-title-tags-from-a-given-html-document-using-beautifulsoup-in-python/)

让我们看看如何使用 python 中的[beauty sup](https://www.geeksforgeeks.org/beautifulsoup-object-python-beautifulsoup/)从给定的 html 文档中查找标题标签。所以我们可以使用 BeautifulSoup find()方法从 html 文档中找到标题标签。find 函数将标签的名称作为字符串输入，并从网页中返回第一个找到的特定标签的匹配项。

**例 1:**

## 蟒蛇

```py
# import BeautifulSoup
from bs4 import BeautifulSoup

# create html document
html = """
      <html>
            <head>
                  <title>   GREEKSFORGREEKS   </title>
            </head>
      <body>

<p>     GFG BeautifulSoup tutorial
             </p>

      </body>
     </html>
"""

# invoke BeautifulSoup()
soup = BeautifulSoup(html, 'html.parser')
print("  ***  Title of the document  ***  ")

# invoke find()
print(soup.find("title"))
```