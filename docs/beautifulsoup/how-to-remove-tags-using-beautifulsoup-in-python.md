# 如何在 Python 中使用 BeautifulSoup 移除标签？

> 原文:[https://www . geesforgeks . org/how-to-remove-tags-using-beautulsup-in-python/](https://www.geeksforgeeks.org/how-to-remove-tags-using-beautifulsoup-in-python/)

**先决条件-** [美丽组合模块](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

在本文中，我们将起草一个 python 脚本，从树中移除一个标签，然后完全销毁它及其内容。为此，使用了模块内置的分解()方法。

**语法:**

```
Beautifulsoup.Tag.decompose()

```

tag . declaration()从给定的 HTML 文档的树中移除一个标签，然后完全销毁它及其内容。

**实施:**

**例 1:**

## 蟒蛇 3

```
# import module
from bs4 import BeautifulSoup

# URL for scrapping data 
markup = '<a href="https://www.geeksforgeeks.org/">Welcome to <i>geeksforgeeks.com</i></a>'

# get URL html 
soup = BeautifulSoup(markup, 'html.parser')

# display before decompose
print("Before Decompose")
print(soup.a)

# decomposing the
# soup data
new_tag = soup.a.decompose()
print("After decomposing:")
print(new_tag)
```

**输出:**

> 分解前
> 
> [欢迎来到*geeksforgeeks.com*T3】](”https://www.geeksforgeeks.org/”)
> 
> 分解后:
> 
> 无

**例 2:** 实现给定的 URL 来刮除 HTML 文档。

## 蟒蛇 3

```
# import module
from bs4 import BeautifulSoup
import requests

# Get URL html
# Scraping the data from
# Html doc
url = 'https://www.geeksforgeeks.org/'
reqs = requests.get(url)
soup = BeautifulSoup(reqs.text, 'html.parser')

# Before decomposing
print("Before Decomposing")
print(soup)

# decompose the soup
result = soup.decompose()
print("After decomposing:")
print(result)
```

**输出:**

> 分解前
> 
> ..
> 
> ……
> 
> 分解后:
> 
> 无