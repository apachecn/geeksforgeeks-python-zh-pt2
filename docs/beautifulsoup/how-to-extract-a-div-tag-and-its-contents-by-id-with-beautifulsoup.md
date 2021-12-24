# 如何用 BeautifulSoup 按 id 提取 div 标签及其内容？

> 原文:[https://www . geeksforgeeks . org/如何通过 id-with-beauty sup 提取一个 div-tag-及其内容/](https://www.geeksforgeeks.org/how-to-extract-a-div-tag-and-its-contents-by-id-with-beautifulsoup/)

是一个用于网页抓取的 Python 库。这个强大的 python 工具也可以用来修改 HTML 网页。本文描述了如何通过 div 的 ID 来提取 div 及其内容。为此，模块的 find()函数用于通过其 ID 来查找 div。

**进场:**

*   导入模块
*   从网页上删除数据
*   解析抓取到 HTML 的字符串
*   找到带有标识的分区
*   打印其内容

> **语法:** find(tag_name，**kwargs)
> 
> **参数:**
> 
> *   tag_name 参数告诉美丽的汤只查找给定名称的标签。文本字符串将被忽略，名称不匹配的标签也将被忽略。
> *   **kwargs 参数用于根据每个标记的“id”属性进行筛选。

**下面是实现:**

**例 1:**

## 蟒蛇 3

```
#importing module
from bs4 import BeautifulSoup

markup = '''<html><body><div id="container">Div Content</div></body></html>'''
soup = BeautifulSoup(markup, 'html.parser')

#finding the div with the id
div_bs4 = soup.find('div', id = "container")

print(div_bs4.string)
```

**输出:**

```
Div Content
```

**例 2:**

## 蟒蛇 3

```
#importing module
from bs4 import BeautifulSoup

markup =markup = """

<!DOCTYPE>
<html>
  <head><title>Example</title></head>
    <body>

<p>
        Nested div
      </p>

        <div id="first"> Div with ID first
          <div id="second"> Div with id second
          </div>
        </div> 
    </body>
</html>
"""

# parsering string to HTML 
soup = BeautifulSoup(markup, 'html.parser')

#finding the div with the id
div_bs4 = soup.find('div', id = "second")

print(div_bs4.string)
```

**输出:**

```
 Div with id second
```