# 儿童发电机–Python 美化套件

> 原文:[https://www . geesforgeks . org/children-generator-python-beautulsoup/](https://www.geeksforgeeks.org/children-generator-python-beautifulsoup/)

**儿童**生成器由美颜汤提供，美颜汤是一个针对 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。子代生成器用于迭代标记的子代。每个子元素都是标签元素。

**语法:**

```py
tag.children 

```

**下面给出的例子解释了《美丽的汤》中儿童发电机的概念。**
**例 1:** 在这个例子中，我们要得到元素的子元素。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the body tag
tag = soup.body

# Print the children of tag
for child in tag.children:
    print(child)
```

**输出:**

```py
<b> Hello world </b>
<body></body>

```

**例 2:** 在本例中，我们将看到孩子的类型。

## 蟒蛇 3

```py
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Create the document
doc = "<body><b> Hello world </b><body>"

# Initialize the object with the document
soup = BeautifulSoup(doc, "html.parser")

# Get the body tag
tag = soup.body

# Print the type of children of tag
for child in tag.children:
    print(type(child))
```

**输出:**

```py
<class 'bs4.element.Tag'>
<class 'bs4.element.Tag'>

```