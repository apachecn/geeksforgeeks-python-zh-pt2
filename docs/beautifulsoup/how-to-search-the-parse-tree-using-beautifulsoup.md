# 如何使用漂亮的组图搜索解析树？

> 原文:[https://www . geeksforgeeks . org/如何使用-beautiful sup/](https://www.geeksforgeeks.org/how-to-search-the-parse-tree-using-beautifulsoup/)搜索-解析树

搜索解析树意味着我们需要找到标签和 HTML 树的内容。这可以通过多种方式实现。但是搜索解析树最常用的方法是 find()和 find_all()方法。在此帮助下，我们可以使用[美化组](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)解析 HTML 树。

要搜索解析树，请执行以下步骤。

**第一步:**为了进行抓取，我们需要导入美图偶模块，导入[请求](https://www.geeksforgeeks.org/python-requests-tutorial/)方法请求网站页面。

```
from bs4 import BeautifulSoup
import requests
```

**第二步:**第二步将使用 HTML 解析器和美化输出功能创建网站或 HTML 页面的汤。

```
BeautifulSoup(sample_website, 'html.parser')
```

**第三步:**我们可以在汤里用两种方法搜索解析树第一种是 find 方法第二种是 find all 方法。在 find 方法中，它将返回满足条件的第一个 HTML 树，find_all 方法将返回满足条件的所有 HTML 解析树。

**示例 1:** 使用 find()方法

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests

# sample website
sample_website = 'https://www.geeksforgeeks.org/difference-between-article-and-blog/'

# call get method to request the page
page = requests.get(sample_website)

# with the help of BeautifulSoup method and
# html parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

# With the help of find method perform searching 
# in parser tree
print(soup.find('th'))
```

**输出:**

```
<th>S.No.</th>
```

**示例 2:** 使用 find_all()方法

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests

# sample website
sample_website = 'https://www.geeksforgeeks.org/difference-between-article-and-blog/'

# call get method to request the page
page = requests.get(sample_website)

# with the help of BeautifulSoup method and html
# parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

# With the help of find_all method perform searching
# in parser tree
print(soup.find_all('th'))
```

**输出:**

```
[<th>S.No.</th>, <th>ARTICLE</th>, <th>BLOG</th>]
```