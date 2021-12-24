# 美丽套件 Python 中的字符串属性

> 原文:[https://www . geesforgeks . org/string-attribute-in-beautulsoup-python/](https://www.geeksforgeeks.org/string-attribute-in-beautifulsoup-python/)

**字符串**属性由美人汤提供，美人汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。如果一个标签只有一个子标签，并且该子标签是*导航字符串*，则可以使用*访问该子标签。弦*。
**先决条件:** [美人汤安装](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#installing-beautiful-soup)。
**语法:**

```py
 tag.string 

```

**下面给出的例子解释了《美丽的汤》中的弦的概念。**
**例 1:** 在本例中，我们将得到字符串。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the b tag
tag = soup.b

# Print the string
print(tag.string)
```