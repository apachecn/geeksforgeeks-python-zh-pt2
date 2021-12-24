# 内容列表–Python 美化套件

> 原文:[https://www . geesforgeks . org/contents-list-python-beautulsoup/](https://www.geeksforgeeks.org/contents-list-python-beautifulsoup/)

**内容**列表由美汤提供，美汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。内容是包含标签子项的列表。

**语法:**

```py
 tag.contents 

```

**下面给出的例子解释了《美丽的汤》中内容的概念。**
**例 1:** 在本例中，我们将获取元素的内容。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the whole content from the body tag
contents = soup.body.contents

# Print the contents
print(contents)
```

**输出:**

```py
[<b> Hello world </b>, <body></body>]

```

**例 2:** 在本例中，我们将看到内容的类型。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the whole content from the body tag
contents = soup.body.contents

# Print the type of contents
print(type(contents))
```

**输出:**

```py
<type 'list'>

```