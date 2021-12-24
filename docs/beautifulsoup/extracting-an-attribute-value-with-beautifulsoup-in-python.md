# 用 Python 中的漂亮组提取属性值

> 原文:[https://www . geeksforgeeks . org/extracting-a-attribute-value-with-beautiful sup-in-python/](https://www.geeksforgeeks.org/extracting-an-attribute-value-with-beautifulsoup-in-python/)

**先决条件:** [美容套装安装](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#installing-beautiful-soup)

属性由美丽汤提供，这是一个针对 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。标签可以有任意数量的属性。例如，标签**有一个值为“活动”的属性“类”。我们可以通过将标签视为字典来访问它的属性。**

**语法:**

```
tag.attrs

```

**实现:**
**示例 1:** 使用属性提取方法提取属性的程序。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <h2 class="hello"> Heading 1 </h2>
        <h1> Heading 2 </h1>
    </html>
    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Get the attribute
attribute = tag.attrs

# Print the output
print(attribute)
```

**输出:**

```
{'class': ['hello']}

```

**示例 2:** 使用字典方法提取属性的程序。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <h2 class="hello"> Heading 1 </h2>
        <h1> Heading 2 </h1>
    </html>
    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Get the attribute
attribute = tag['class']

# Print the output
print(attribute)
```

**输出:**

```
['hello']

```

**示例 3:** 使用字典方法提取多个属性值的程序。

## 蟒蛇 3

```
# Import Beautiful Soup
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <h2 class="first second third"> Heading 1 </h2>
        <h1> Heading 2 </h1>
    </html>
    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Get the attribute
attribute = tag['class']

# Print the output
print(attribute)
```

**输出:**

```
['first', 'second', 'third']

```