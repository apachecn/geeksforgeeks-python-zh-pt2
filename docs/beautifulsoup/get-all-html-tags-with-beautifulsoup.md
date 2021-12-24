# 用漂亮的组图获取所有 HTML 标签

> 原文:[https://www . geesforgeks . org/get-all-html-tags-with-beautulsup/](https://www.geeksforgeeks.org/get-all-html-tags-with-beautifulsoup/)

网页抓取是一个使用机器人的过程，类似于被称为网页抓取器的软件，从 HTML 或 XML 内容中提取信息。美丽的汤就是这样一个库，用于通过 python 抓取数据。美丽的汤解析网页的 HTML 内容，并收集它来提供迭代、搜索和修改功能。为了提供这些功能，它与将内容转换成解析树的解析器一起工作。使用一个你熟悉的解析器使用漂亮的程序在网页中爬行是相当容易的。

要使用美化组库获取网页的所有 HTML 标签，首先导入美化组并请求库向网页发出 **GET 请求**。

**分步方法:**

*   导入所需模块。

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests
```

*   导入库后，现在用网页的 URL 分配一个 URL 变量，并发出 GET 请求以获取原始 HTML 内容:

## 蟒蛇 3

```py
# Assign URL
url = "https://www.geeksforgeeks.org/"

# Make a GET request to fetch the raw HTML content
html_content = requests.get(url).text
```

*   现在解析 HTML 内容:

## 蟒蛇 3

```py
# Parse the html content using any parser 
soup = BeautifulSoup(html_content,"html.parser")
```

*   现在要获取网页的所有 HTML 标签，运行**循环。使用 find_all()函数命名标签的**属性:

## 蟒蛇 3

```py
[tag.name for tag in soup.find_all()]
```

**下面是完整的程序:**

## 蟒蛇 3

```py
# Import modules
from bs4 import BeautifulSoup
import requests

# Assign URL
url = "https://www.geeksforgeeks.org/"

# Make a GET request to fetch the raw HTML content
html_content = requests.get(url).text

# Parse the html content using any parser
soup = BeautifulSoup(html_content, "html.parser")

# Display HTML tags
[tag.name for tag in soup.find_all()]
```

**输出:**

```py
['html',
 'head',
 'meta',
 'meta',
 'meta',
 'link',
 'meta',
 'meta',
 'meta',
 'meta',
 'meta',
 'script',
 'script',
 'link',
 'title',
 'link',
 'link',
 'script',
 'script']
```