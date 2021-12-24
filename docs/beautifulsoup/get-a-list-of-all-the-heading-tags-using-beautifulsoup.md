# 使用美观组

获得所有标题标签的列表

> 原文:[https://www . geeksforgeeks . org/get-a-list-all-the-heading-tags-using-beautulsoup/](https://www.geeksforgeeks.org/get-a-list-of-all-the-heading-tags-using-beautifulsoup/)

为了使用美观组打印所有标题标签，我们使用 **find_all()** 方法。find_all 方法是美化组中最常用的方法之一。它查看标签并检索该标签的所有出现。

> **语法:** find_all(name，attrs，recursive，string，limit，**kwargs)

一个 HTML 文档由以下标签组成——h1、h2、h3、h4、h5 和 h6。网页中最常用的 HTML 标签是 h1、h2 和 h3，为了找到这些标签，我们将一个标签列表作为参数传递给 find_all()方法。

**步骤:**

1.  Import library [requests](https://www.geeksforgeeks.org/python-requests-tutorial/) and [beautification group](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)
2.  Pass URL to variable
3.  Get URL using request library
4.  Create beautification group object
5.  Create a title tag list ()
6.  Use **find _ all ()** method.

**例:**

## 蟒 3

```
# Python program to print all heading tags
import requests
from bs4 import BeautifulSoup

# scraping a wikipedia article
url_link = 'https://www.geeksforgeeks.org/how-to-scrape-all-pdf-files-in-a-website/'
request = requests.get(url_link)

Soup = BeautifulSoup(request.text, 'lxml')

# creating a list of all common heading tags
heading_tags = ["h1", "h2", "h3"]
for tags in Soup.find_all(heading_tags):
    print(tags.name + ' -> ' + tags.text.strip())
```

**输出:**

```
h2 -> Related Articles
h2 -> Python3
h2 -> Python3
h2 -> Python3
h2 -> Python3
h2 -> Python3
h2 -> Python3
```