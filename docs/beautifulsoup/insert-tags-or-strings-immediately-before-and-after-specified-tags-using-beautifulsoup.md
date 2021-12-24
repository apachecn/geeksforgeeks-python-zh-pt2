# 在指定标签的前后插入标签或字符串

> 原文:[https://www . geeksforgeeks . org/insert-tags-or-strings-紧接在指定标记之前和之后-使用-beauty ulsoup/](https://www.geeksforgeeks.org/insert-tags-or-strings-immediately-before-and-after-specified-tags-using-beautifulsoup/)

美化程序是一个 Python 库，用于从标记语言中提取数据，如超文本标记语言、可扩展标记语言等。例如，假设我们有一些网页需要显示与一些研究相关的相关数据，如处理日期或地址等信息，但没有任何方法下载，在这种情况下，美化组对我们来说很方便，因为它帮助我们从 HTML 页面中提取特定内容并保存信息。美化组是一种有效的网页抓取工具，有助于清理和解析从网页中提取的文档。

### **所需库的安装:**

*   **bs4:** 由于默认情况下 python 中不提供 BeautifulSoup，我们需要使用下面带有 pip 的命令将其安装到我们的机器中。

```py
pip install bs4
```

*   **lxml:** lxml 是 pythonic libxml2 和 libxlst 库的成熟绑定，借助 ElementTree API，它提供了对这些库的安全便捷的访问。

```py
pip install lxml
```

### **使用的功能:**

*   **tag():** Python 实现，用于在指定标签前插入标签或字符串，并带有美化组。
*   **insert():** 美化组中的 insert()函数用于将元素插入到标签对象中，很像。python 列表中的惰性()。
*   **insert _ before():**insert _ before()方法在解析树中的其他内容之前插入标签或字符串。
*   **insert _ after():**insert _ after 方法在给定的解析树中插入跟在其他东西后面的标签或字符串。

### **分步方法:**

*   首先，我们使用 bs4 导入一个美丽的输出库。
*   我们将一个属性分配给美化组，并使用我们试图实现程序的源 url 来填充它。
*   我们使用 new_tag()在标记对象中分配一个新元素。
*   我们给标记对象分配一个字符串，以便在它之前或之后附加我们的标记(如指定的)。
*   我们使用 insert_before()函数在字符串前插入标记。

### 实施:

**示例 1:** Python 实现，用于在指定标签前插入标签或字符串，并带有美化组。

## 蟒 3

```py
# import module
from bs4 import BeautifulSoup

# assign URL
s = BeautifulSoup("<b>www.geeksforgeeks.com</b>", 
                  "lxml")

print("Original Markup:")
print(s.b)

# insert tag
tag = s.new_tag("k")
tag.string = "Python"

print("\nNew Markup, before inserting the text:")
s.b.string.insert_before(tag)
print(s.b)
```