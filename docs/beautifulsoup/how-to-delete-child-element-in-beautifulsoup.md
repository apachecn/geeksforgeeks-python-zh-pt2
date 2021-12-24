# 如何删除美化组中的子元素？

> 原文:[https://www . geesforgeks . org/如何删除子元素 in-beauty ulsup/](https://www.geeksforgeeks.org/how-to-delete-child-element-in-beautifulsoup/)

是一个用于网页抓取的 Python 库。这个强大的 python 工具也可以用来修改 html 网页。本文描述了如何使用美丽的组来删除子元素。为此，使用了模块的各种方法。

**使用的方法:**

*   **clear():** Tag.clear()从给定 HTML 文档的树中删除标签。
*   **分解():** 标签.分解()从给定 HTML 文档的树中移除一个标签，然后完全销毁它及其内容。
*   **replace():**tag . replace()用新标签替换特定标签。

**进场:**

*   导入模块。
*   从网页上删除数据。
*   解析抓取到 html 的字符串。
*   查找要删除其子元素的标记。
*   使用以下任何方法:清除()、分解()或替换()。
*   打印替换的内容。

**例 1:**

## 蟒蛇 3

```py
# importing module
from bs4 import BeautifulSoup

markup = """

<!DOCTYPE>
<html>
  <head><title>Example</title></head>
  <body>
  <div id="parent">

<p>
    This is child of div with id = "parent".
    <span>Child of "P"</span>
  </p>

  <div>
  Another Child of div with id = "parent".
  </div>
  </div>

<p>
  Piyush
  </p>

  </body>
</html>
"""

# parsering string to HTML
soup = BeautifulSoup(markup, 'html.parser')

# finding tag whose child to be deleted
div_bs4 = soup.find('div')

# delete the child element
div_bs4.clear()

print(div_bs4)
```

**输出:**

```py
<div id="parent"></div>
```

**例 2:**

## 蟒蛇 3

```py
# importing module
from bs4 import BeautifulSoup

markup = """

<!DOCTYPE>
<html>
  <head><title>Example</title></head>
  <body>
  <div id="parent">

<p>
    This is child of div with id = "parent".
    <span>Child of "P"</span>
  </p>

  <div>
  Another Child of div with id = "parent".
  </div>
  </div>

<p>
  Piyush
  </p>

  </body>
</html>
"""

# parsering string to HTML
soup = BeautifulSoup(markup, 'html.parser')

# finding tag whose child to be deleted
div_bs4 = soup.find('div')

# delete the child element
div_bs4.decompose()

print(div_bs4)
```

**输出:**

```py
<None></None>
```

**例 3:**

## 蟒蛇 3

```py
# importing module
from bs4 import BeautifulSoup

markup = """

<!DOCTYPE>
<html>
  <head><title>Example</title></head>
  <body>
  <div id="parent">

<p>
    This is child of div with id = "parent".
    <span>Child of "P"</span>
  </p>

  <div>
  Another Child of div with id = "parent".
  </div>
  </div>

<p>
  Piyush
  </p>

  </body>
</html>
"""

# parsering string to HTML
soup = BeautifulSoup(markup, 'html.parser')

# finding tag whose child to be deleted
div_bs4 = soup.find('div')

# delete the child element
div_bs4.replaceWith('')

print(div_bs4)
```

**输出:**

```py
<div id="parent">
<p>
    This is child of div with id = "parent".
    <span>Child of "P"</span>
</p>
<div>
  Another Child of div with id = "parent".
  </div>
</div>
```