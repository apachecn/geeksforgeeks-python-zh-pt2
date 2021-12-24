# 使用美化组

检索 html 标签的子标签

> 原文:[https://www . geeksforgeeks . org/retrieve-the-children-of-html-tag-using-beautulsoup/](https://www.geeksforgeeks.org/retrieve-children-of-the-html-tag-using-beautifulsoup/)

**先决条件:** [美丽组合](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

美化程序是一个 Python 模块，用于网页抓取。本文讨论如何抓取和显示给定 HTML 标签的子标签。

**样本网站:**[https://www.geeksforgeeks.org/caching-page-tables/](https://www.geeksforgeeks.org/caching-page-tables/)

### **第一个孩子:**

**接近**

*   导入模块
*   传递网址
*   请求页面
*   使用 findChild()函数显示第一个孩子

**语法:**

> findChild()

**示例:**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample web page
sample_web_page = 'https://www.geeksforgeeks.org/caching-page-tables/'

# call get method to request that page
page = requests.get(sample_web_page)

# with the help of beautifulSoup and html parser create soup
soup = BeautifulSoup(page.content, "html.parser")

child_soup = soup.find('p')

print("child :  ", child_soup.findChild())
```

**输出:**

> 子级:[分页](”https://www.geeksforgeeks.org/paging-in-operating-system/”)

### **适用于所有儿童:**

要检索 HTML 标签的子标签，我们必须选择使用**。儿童**或**。内容**。孩子和内容的区别是孩子不占用任何内存它给我们一个可重复的列表，内容给孩子一个标签，但是它使用内存。对于大的 HTML 文件来说，使用子文件是一个更好的选择，而对于存储值来说，需要的内容会更好。

**接近**

*   导入模块
*   传递网站网址
*   请求页面
*   使用任一关键字显示子标签

**使用。儿童:**

为了找回所有的孩子。孩子会被利用。

**示例:**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample web page
sample_web_page = 'https://www.geeksforgeeks.org/caching-page-tables/'

# call get method to request that page
page = requests.get(sample_web_page)

# with the help of beautifulSoup and html parser create soup
soup = BeautifulSoup(page.content, "html.parser")
child_soup = soup.find('p')

for i in child_soup.children:
    print("child :  ", i)
```

**输出:**

> 子级:[分页](”https://www.geeksforgeeks.org/paging-in-operating-system/”)
> 
> child:是一种内存管理方案，它允许进程的物理地址空间是非连续的。分页的基本思想是将物理内存分成固定大小的块，称为
> 
> 子:**帧**
> 
> 子级:将逻辑内存分成大小相同的块，称为
> 
> 子:**页**
> 
> 孩子:。在执行该过程时，该过程所需的页面被从它们的源(即盘或任何备份存储设备)加载到可用的帧中。

**使用。内容**

它还会返回所有的子标签，并将它们存储在内存中。

**例**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample web page
sample_web_page = 'https://www.geeksforgeeks.org/caching-page-tables/'

# call get method to request that page
page = requests.get(sample_web_page)

# with the help of beautifulSoup and html parser create soup
soup = BeautifulSoup(page.content, "html.parser")

child_soup = soup.find('p')

print("child :  ", child_soup.contents)
```

**输出**

> child : [ [分页](”https://www.geeksforgeeks.org/paging-in-operating-system/”)，'是一种内存管理方案，允许进程的物理地址空间是非连续的。分页的基本思想是将物理内存分成固定大小的块，称为“，**帧**，将逻辑内存分成相同大小的块，称为“，**页**，”。在执行该过程时，该过程所需的页面会从其源(即磁盘或任何备份存储设备)加载到可用的帧中。]