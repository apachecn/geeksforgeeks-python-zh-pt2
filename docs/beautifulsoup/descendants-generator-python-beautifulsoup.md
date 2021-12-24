# 后代生成器–Python 美化程序

> 原文:[https://www . geesforgeks . org/后代-生成器-python-beautulsoup/](https://www.geeksforgeeks.org/descendants-generator-python-beautifulsoup/)

**后代**生成器由美人汤提供，美人汤是 Python 的一个网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。*。目录*和*。孩子*属性只考虑一个标签的直接孩子。后代生成器用于递归地遍历标签的所有子标签。每个子元素都将成为元素的标记元素和字符串的导航字符串。

**语法:**

```
 tag.descendants 

```

**下面给出的例子解释了《美人汤》中后代生成器的概念。**
**例 1:** 在这个例子中，我们要得到一个元素的后代。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the body tag
tag = soup.body

# Print all the descendants of tag
for descendant in tag.descendants:
    print(descendant)
```

**输出:**

```
<b> Hello world </b>
 Hello world 
<body></body>

```

**例 2:** 在本例中，我们将看到后代的类型。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the body tag
tag = soup.body

# Print the type of the descendants of tag
for descendant in tag.descendants:
    print(type(descendant))
```

**输出:**

```
<class 'bs4.element.Tag'>
<class 'bs4.element.NavigableString'>
<class 'bs4.element.Tag'>

```