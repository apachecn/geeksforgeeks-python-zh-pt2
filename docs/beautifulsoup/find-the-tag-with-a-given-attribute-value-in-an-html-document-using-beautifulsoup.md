# 在 HTML 文档中使用“美化组”找到具有给定属性值的标签

> 原文:[https://www . geesforgeks . org/find-the-tag-with-a-给定属性-值-in-html-document-using-beauty ulsup/](https://www.geeksforgeeks.org/find-the-tag-with-a-given-attribute-value-in-an-html-document-using-beautifulsoup/)

**先决条件:** [美丽组合](https://www.geeksforgeeks.org/beautifulsoup-object-python-beautifulsoup/)

在本文中，我们将讨论如何在 HTML 文档中使用 beautifulsoup 来查找具有给定属性值的标签。

**进场:**

*   导入模块。
*   从网页上删除数据。
*   解析刮到 HTML 的字符串。
*   使用 find()函数查找属性和标签。
*   打印结果。

> **语法:**查找(attr_name=“值”)

以下是上述方法的一些实现:

**例 1:**

## 蟒蛇 3

```py
# importing module 
from bs4 import BeautifulSoup 

markup = '''<html><body><div id="container">Div Content</div></body></html>'''
soup = BeautifulSoup(markup, 'html.parser') 

# finding the tag with the id attribute
div_bs4 = soup.find(id = "container") 

print(div_bs4.name)
```

**输出:**

```py
div
```

**例 2:**

## 蟒蛇 3

```py
# importing module 
from bs4 import BeautifulSoup 

markup = '''<html><body><a href="https://www.geeksforgeeks.org/">Geeks for Geeks</a></body></html>'''
soup = BeautifulSoup(markup, 'html.parser') 

# finding the tag with the href attribute
div_bs4 = soup.find(href = "https://www.geeksforgeeks.org/") 

print(div_bs4.name)
```

**输出:**

```py
a
```

**例 3:**

## 蟒蛇 3

```py
# importing module 
from bs4 import BeautifulSoup 

markup = """<html><head><title>Welcome  to geeksforgeeks</title></head> 
<body> 
<p class="title"><b>Geeks</b></p>

<p class="gfg">geeksforgeeks a computer science portal for geeks 
</body> 
"""
soup = BeautifulSoup(markup, 'html.parser') 

# finding the tag with the class attribute
div_bs4 = soup.find(class_ = "gfg") 

print(div_bs4.name)
```

**输出:**

```py
p
```