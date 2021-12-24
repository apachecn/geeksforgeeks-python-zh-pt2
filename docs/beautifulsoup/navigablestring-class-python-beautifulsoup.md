# 导航字符串类–Python 美化程序

> 原文:[https://www . geesforgeks . org/navigablestring-class-python-beautulsoup/](https://www.geeksforgeeks.org/navigablestring-class-python-beautifulsoup/)

**navigatablestring**类由美颜汤提供，美颜汤是一个针对 Python 的网页抓取框架。网页抓取是使用自动化工具从网站中提取数据的过程，以使该过程更快。字符串对应于标签中的一位文本。美丽的汤使用导航字符串类来包含这些文本。

**语法:**

```
<tag> String here </tag>

```

**下面给出的例子解释了《美丽的汤》中 NavigableString 类的概念。**
**例 1:** 在本例中，我们将看到字符串的类型。

## 蟒蛇 3

```
# Import Beautiful Soup
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

# Get the string inside the tag
string = tag.string

# Print the type
print(type(string))
```

**输出:**

```
<class 'bs4.element.NavigableString'>

```

**示例 2:** 在本例中，我们将把 NavigableString 转换为 Unicode 字符串。

## 蟒蛇 3

```
# Import Beautiful Soup
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

# Get the string inside the tag and convert 
# it into string
string = str(tag.string)

# Print the type
print(type(string))
```

**输出:**

```
<type 'str'>

```