# 使用漂亮的组图

显示标签内的文本

> 原文:[https://www . geesforgeks . org/show-text-in-the-tags-using-beautulsup/](https://www.geeksforgeeks.org/show-text-inside-the-tags-using-beautifulsoup/)

**先决条件:**

*   [请求](https://www.geeksforgeeks.org/python-requests-tutorial/)
*   [美丽的脉冲星](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

在本文中，我们将学习如何使用美丽的输出从 HTML 标签中获取文本。这里我们将使用 Python 中的 [**请求**](https://www.geeksforgeeks.org/get-post-requests-using-python/) & **美化程序**模块。

**请求**库是 Python 的一个组成部分，用于向指定的网址发出 HTTP 请求。无论是 REST APIs 还是 Web 报废，都必须了解请求，以便进一步使用这些技术。当一个人向 URI 提出请求时，它会返回一个响应。Python 请求提供了管理请求和响应的内置功能。

```py
pip install requests
```

**美汤**是一个 Python 库，专为像刮屏这样的快速周转项目而设计。

```py
pip install beautifulsoup4
```

**方法 1:** 我们可以使用**文字**属性。它将只打印标签中的文本。

## 蟒蛇 3

```py
# Import Required Module
import requests 
from bs4 import BeautifulSoup

# Web URL
Web_url = "https://www.geeksforgeeks.org/"

# Get URL Content
r = requests.get(Web_url) 

# Parse HTML Code
soup = BeautifulSoup(r.content, 'html.parser')

tag = soup.find("p")

print(tag.text)
```

**输出:**

```py
Skip to content
```

**方法二:**我们也可以用 **get_text()** 方法。此方法用于打印网页的整个文本

## 蟒蛇 3

```py
# Import Required Module
import requests 
from bs4 import BeautifulSoup

# Web URL
Web_url = "https://www.geeksforgeeks.org/"

# Get URL Content
r = requests.get(Web_url) 

# Parse HTML Code
soup = BeautifulSoup(r.content, 'html.parser')

tag = soup.find("p")

print(tag.get_text())
```

**输出:**

```py
February 1, 2021
```

**方法 3:** 如果标签中只有一个字符串，那么我们可以使用**字符串**属性。

## 蟒蛇 3

```py
# Import Required Module
import requests 
from bs4 import BeautifulSoup

# Web URL
Web_url = "https://www.geeksforgeeks.org/"

# Get URL Content
r = requests.get(Web_url) 

# Parse HTML Code
soup = BeautifulSoup(r.content, 'html.parser')

tag = soup.find("p")

print(tag.string)
```

**输出:**

```py
February 1, 2021
```