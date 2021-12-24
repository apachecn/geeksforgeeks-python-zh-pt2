# 用漂亮的组图把 HTML 转换成文本

> 原文:[https://www . geeksforgeeks . org/converting-html-to-text-with-beautiful sup/](https://www.geeksforgeeks.org/converting-html-to-text-with-beautifulsoup/)

很多时候，在使用网络自动化时，我们需要将 HTML 代码转换为文本。这可以使用漂亮的套件来完成。本模块提供 get_text()函数，以 HTML 为输入，返回文本为输出。

**例 1:**

## 蟒 3

```py
# importing the library
from bs4 import BeautifulSoup

# Initializing variable
gfg = BeautifulSoup("<b>Section </b><br/>BeautifulSoup<ul>\
<li>Example <b>1</b></li>")

# Calculating result
res = gfg.get_text()

# Printing the result
print(res)
```