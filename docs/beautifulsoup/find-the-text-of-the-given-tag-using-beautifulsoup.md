# 使用“美化组”

找到给定标签的文本

> 原文:[https://www . geeksforgeeks . org/find-the-text-of-the-given-tag-using-beautulsoup/](https://www.geeksforgeeks.org/find-the-text-of-the-given-tag-using-beautifulsoup/)

网页抓取是使用称为网页抓取器的软件机器人从网页的 HTML 或 XML 内容中提取信息的过程。**美人汤**是一个通过 python 进行数据抓取的库。美丽汤与**解析器**一起工作，提供迭代、搜索和修改解析器提供的内容(以解析树的形式)。使用“美丽的汤”在网页中爬行并找到给定标签的文本相当容易。

在本文中，我们将讨论从给定的标签中找到文本。

**分步方法:**

*   首先导入库。

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests
```

*   现在分配网址。

## 蟒蛇 3

```py
# assign URL
url = "https://www.geeksforgeeks.org/"
```

*   从网址中获取原始的 HTML 内容。

## 蟒蛇 3

```py
html_content = requests.get(url).text
```

*   现在分析一下内容。

## 蟒蛇 3

```py
# Now that the content is ready, iterate 
# through the content using BeautifulSoup
soup = BeautifulSoup(html_content, "html.parser")
```

*   解析内容后，我们搜索特定的标签并打印其文本。

## 蟒蛇 3

```py
print(soup.find('title'))
```

**下面是完整的程序。**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# Assign URL
url = "https://www.geeksforgeeks.org/"

# Fetch raw HTML content
html_content = requests.get(url).text

# Now that the content is ready, iterate 
# through the content using BeautifulSoup:
soup = BeautifulSoup(html_content, "html.parser")

# similarly to get all the occurences of a given tag
print(soup.find('title').text)
```

**输出:**

![](img/07e9818cd1e054df40e4e7fcd8bf60d8.png)

**类似地获取给定标签的所有出现:**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# Assign URL
url = "https://www.geeksforgeeks.org/"

# Fetch raw HTML content
html_content = requests.get(url).text

# Now that the content is ready, iterate 
# through the content using BeautifulSoup:
soup = BeautifulSoup(html_content, "html.parser")

# similarly to get all the occurences of a given tag
texts = soup.find_all('p')
for text in texts:
    print(text.get_text())
```

**输出:**

![](img/fb905a6b13c32df233ca69c79f425819.png)