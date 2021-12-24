# 使用 Python 中的美化程序获得标签名称

> 原文:[https://www . geesforgeks . org/get-tag-name-use-beautulsup-in-python/](https://www.geeksforgeeks.org/get-tag-name-using-beautifulsoup-in-python/)

**先决条件:** [美容套装安装](https://www.geeksforgeeks.org/beautifulsoup-installation-python/)

**名称**属性由美颜汤提供，美颜汤是 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。名称对象对应于原始文档中的 XML 或 HTML 标记的名称。

**语法:**

```
tag.name
```

**参数:**该函数不接受任何参数。

**实现:**
**示例 1:** 提取 XML 标签名称的程序。

## 蟒蛇 3

```
# Import module
from bs4 import BeautifulSoup

# Initialize the object with a XML
soup = BeautifulSoup('''
    <root>
        <name_of_tag>the first strong tag</name_of_tag>
    </root>
    ''', "lxml")

# Get the tag
tag = soup.name_of_tag

# Get the tag name
name = tag.name

# Print the output
print(name)
```

**输出:**

```
name_of_tag

```

**示例 2:** 解释 HTML 标签的上述功能的程序。

## 蟒蛇 3

```
# Import module
from bs4 import BeautifulSoup

# Initialize the object with a HTML page
soup = BeautifulSoup('''
    <html>
        <h2> Heading 1 </h2>
        <h1> Heading 2 </h1>
    </html>
    ''', "lxml")

# Get the whole h2 tag
tag = soup.h2

# Get the name of the tag
name = tag.name

# Print the output
print(name)
```

**输出:**

```
h2
```