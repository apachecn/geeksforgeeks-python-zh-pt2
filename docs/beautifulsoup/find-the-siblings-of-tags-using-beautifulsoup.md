# 使用“漂亮的组”找到标签的兄弟标签

> 原文:[https://www . geeksforgeeks . org/find-the-同辈标签-使用-beautulsoup/](https://www.geeksforgeeks.org/find-the-siblings-of-tags-using-beautifulsoup/)

**先决条件:** [美丽组](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

**美化程序(bs4)** 是一个 Python 库，用于从 HTML 和 XML 文件中拉出数据。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。在这篇文章中，我们将学习使用美丽的输出在 HTML 标签中的兄弟。

这里我们将讨论这四个兄弟属性:

*   **previous_sibling** 用于查找给定元素的前一个元素
*   **next_sibling** 用于查找给定元素的下一个元素
*   **previous _ 同胞**用于查找给定元素的所有先前元素
*   **next _ 同胞**用于查找给定元素的所有下一个元素

**接近**

*   导入模块
*   加载或创建 HTML 代码
*   解析 HTML 代码
*   打印必需的同级。

**示例 1:** 打印下一个直接同级

## 蟒蛇 3

```
# Import Module
from bs4 import BeautifulSoup

# HTML CODE
html_code = """<a><b>text1</b><c>text2</c></a>"""

# Parse HTML CODE
soup = BeautifulSoup(html_code, 'html.parser')

# next element
print(soup.b.next_sibling)
```

**输出:**

> <c>文本 2</c>

**示例 2:** 获取上一个直接同级

## 蟒蛇 3

```
# Import Module
from bs4 import BeautifulSoup

# HTML CODE
html_code = """<a><b>text1</b><c>text2</c></a>"""

# Parse HTML CODE
soup = BeautifulSoup(html_code, 'html.parser')

# previous element
print(soup.c.previous_sibling)
```

**输出:**

> **文本 1**

假设我们想要找到标签的所有下一个元素。为此，我们只是简单地遍历兄弟并打印所需的标签。

**示例 3:** 获取标签旁边的所有兄弟

## 蟒蛇 3

```
# Import Module
from bs4 import BeautifulSoup

# HTML CODE
html_code = """<a><b>text1</b><d>text3</d><c>text2</c></a>"""

# Parse HTML CODE
soup = BeautifulSoup(html_code, 'html.parser')

# next element
for element in soup.b.next_siblings:
    print(element)
```

**输出:**

> <d>文本 3</d>
> 
> <c>文本 2</c>

**示例 4:** 获取所有先前的兄弟

## 蟒蛇 3

```
# Import Module
from bs4 import BeautifulSoup

# HTML CODE
html_code = """<a><b>text1</b><d>text3</d><c>text2</c></a>"""

# Parse HTML CODE
soup = BeautifulSoup(html_code, 'html.parser')

# previous element
for element in soup.c.previous_siblings:
    print(element)
```

**输出:**

> <d>文本 3</d>
> 
> **文本 1**