# 如何使用 Python 中的 Beautifulsoup 从 body tag 中刮除所有文本？

> 原文:[https://www . geesforgeks . org/how-to-scratch-the-text-from-tag-use-beauty-oup-in-python/](https://www.geeksforgeeks.org/how-to-scrape-all-the-text-from-body-tag-using-beautifulsoup-in-python/)

**字符串**生成器由美人汤提供，美人汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。*字符串*属性的一个缺点是，它只对内部有字符串的标签有效，而对内部有更多标签的标签不返回任何内容。因此，为了解决这个问题，字符串生成器被用来递归地获取标签中的所有字符串。

**语法:**

```
tag.strings 
```

**下面给出的例子解释了《美丽的汤》中琴弦的概念。**
**例 1:** 在本例中，我们将获得字符串。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><h1> New heading </h1><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the whole body tag
tag = soup.body

# Print each string recursively
for string in tag.strings:
    print(string)
```

**输出:**

```
 Hello world 
 New heading 
```

**例 2:**

## 蟒蛇 3

```
import requests
from bs4 import BeautifulSoup

# url of the website
doc = "https://www.geeksforgeeks.org"

# getting response object
res = requests.get(doc)

# Initialize the object with the document
soup = BeautifulSoup(res.content, "html.parser")

# Get the whole body tag
tag = soup.body

# Print each string recursively
for string in tag.strings:
    print(string)
```

**输出:**

<video class="wp-video-shortcode" id="video-498010-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201013130526/web-scrape-text-python.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201013130526/web-scrape-text-python.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201013130526/web-scrape-text-python.webm)</video>