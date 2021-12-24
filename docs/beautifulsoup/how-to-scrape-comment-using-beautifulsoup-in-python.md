# 如何用 Python 中的 Beautifulsoup 刮评论？

> 原文:[https://www . geesforgeks . org/how-to-scratch-comment-using-beauty-ulsup-in-python/](https://www.geeksforgeeks.org/how-to-scrape-comment-using-beautifulsoup-in-python/)

**评论**由美颜汤提供，美颜汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。注释对象只是一种特殊类型的导航字符串，用于提高代码库的可读性。

**语法:**

```py
<!-- COMMENT --> 

```

**下面给出的例子解释了《美丽的汤》中评论的概念。**
**例 1:** 在这个例子中，我们要创建一个评论。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<b><!-- COMMENT --></b>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the whole comment inside b tag
comment = soup.b

# Print the comment
print(comment)
```

**输出:**

```py
<b><!-- COMMENT --></b>

```

**示例 2:** 在本例中，我们将创建一个注释并查看其类型。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<b><!-- COMMENT --></b>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the whole comment inside b tag
comment = soup.b.string

# Print the type of the comment
print(type(comment))
```

**输出:**

```py
<class 'bs4.element.Comment'> 

```