# 美观组合–通过标签内的文本进行搜索

> 原文:[https://www . geeksforgeeks . org/beautulsoup-按文本搜索-在标签内/](https://www.geeksforgeeks.org/beautifulsoup-search-by-text-inside-a-tag/)

**先决条件:** [美丽组合](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

是一个强大的 python 模块，用于网页抓取。本文讨论如何在给定的标签中搜索特定的文本。

### **接近**

*   导入模块
*   传递网址
*   请求页面
*   指定要搜索的标签
*   对于标签内的文本搜索，我们需要在字符串函数的帮助下检查条件。
*   string 函数将返回标签中的文本。
*   当我们将导航标签，然后我们将检查与文本的条件。
*   返回文本

我们将通过两种方法在标签中看到搜索文本。

### **方法一:迭代**

此方法使用 for 循环来搜索文本。

**例**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample web page
sample_web_page = 'https://www.geeksforgeeks.org/caching-page-tables/'

# call get method to request that page
page = requests.get(sample_web_page)

# with the help of beautifulSoup and html parser create soup
soup = BeautifulSoup(page.content, "html.parser")

child_soup = soup.find_all('strong')

text = 'page table base register (PTBR)'

# we will search the tag with in which text is same as given text
for i in child_soup:
    if(i.string == text):
        print(i)
```

**输出**

> **页表基址寄存器(PTBR)**

### 方法 2:使用λ

这是上述示例的一个线性替代方案。

**例**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample web page
sample_web_page = 'https://www.geeksforgeeks.org/caching-page-tables/'

# call get method to request that page
page = requests.get(sample_web_page)

# with the help of beautifulSoup and html parser create soup
soup = BeautifulSoup(page.content, "html.parser")

text = 'CS Theory Course'

# Search by text with the help of lambda function
gfg = soup.find_all(lambda tag: tag.name == "strong" and text in tag.text)

print(gfg)
```

**输出**

> 【 **CS 理论课程**】