# 更改标签的内容，并使用“美化组”

替换为给定的字符串

> 原文:[https://www . geeksforgeeks . org/change-the-tags-contents-and-replace-to-给定字符串-use-beauty sup/](https://www.geeksforgeeks.org/change-the-tags-contents-and-replace-with-the-given-string-using-beautifulsoup/)

**先决条件:** [美丽组合](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

是一个用于网页抓取的 Python 库。这个强大的 python 工具也可以用来修改 html 网页。本文描述了如何使用美丽的组合来更改标签中的内容，并用给定的字符串替换要更改的内容。为此，使用模块的 replace_with()函数。

**语法:**

> 替换为(“字符串”)

**方法:**

*   Import module
*   Delete data from a Web page
*   Parse the deleted string into html
*   Select the label that needs to be replaced.
*   Use the replace_with () function to add a string instead of an existing string.
*   Print the replaced content.

**程序:**

## 蟒 3

```py
# importing BeautifulSoup Module
from bs4 import BeautifulSoup

markup = '<a href="http://gfg.com/">Geeks for Geeks <i>gfg.com</i></a>'

# parsering string to HTML
soup = BeautifulSoup(markup, 'html.parser')

# tag to be replaced
old_tag = soup.a

# new tag
new_tag = soup.new_tag("p")

# input string
new_tag.string = "gfg.in"

'''replacing tag
#page_element.replace_with("string") removes a tag or string from the tree,
#and replaces it with the tag or string of your choice.'''
old_tag.i.replace_with(new_tag)

print(old_tag)
```

**输出:**

> <a href = " http://gfg . com/">Geeks for Geeks<p>gfg . in</p></a>