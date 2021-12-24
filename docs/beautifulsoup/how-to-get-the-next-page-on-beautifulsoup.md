# 如何在 BeautifulSoup 上进入下一页？

> 原文:[https://www . geeksforgeeks . org/如何进入下一页-on-beautiful sup/](https://www.geeksforgeeks.org/how-to-get-the-next-page-on-beautifulsoup/)

在这篇文章中，我们将看到如何获得下一页的美丽组合。

### 需要的模块

*   [**beauty Soup:**](https://www.geeksforgeeks.org/how-to-scrape-websites-with-beautifulsoup-and-python/)beauty Soup(bs4)是一个用于从 HTML 和 XML 文件中拉出数据的 Python 库。要安装此模块，请在终端中键入以下命令。

```py
pip install bs4
```

*   [**请求** :](https://www.geeksforgeeks.org/python-requests-tutorial/) 这个库可以让你极其轻松的发送 HTTP/1.1 请求。要安装此模块，请在终端中键入以下命令。

```py
pip install requests
```

**进场:**

获得下一页上的美化组意味着首先我们将废弃一页内容，如果页面上有许多链接，我们也想废弃它们。我们可以先得到下一页，然后我们将废弃样本网站，任何其他链接找到，我们将再次调用请求。获取该页面的方法，并将创建一个该页面的汤。这样我们就可以进入下一页。

**让我们一步步执行脚本:**

**第一步:**导入所有依赖

```py
from bs4 import BeautifulSoup
import requests
```

**第二步:**我们需要用请求请求页面 URL。

```py
page=requests.get(sample_website)
```

**第三步:**借助 beautifulsoup 方法和 HTML 解析器，我们将创建一个页面的汤。

```py
soup = BeautifulSoup(page, 'html.parser')
```

**第四步:**

我们将在解析树中搜索并找到链接。如果我们想要这个网址，那么在请求模块和美丽模块的帮助下，我们将再次创建下一页的汤，这样我们就可以在美丽的页面上获得下一页。

## 蟒蛇 3

```py
for i in soup.find_all('a', href = True):

  # check all link which is contain
  # "www.geeksforgeeks.org" string 
  if("www.geeksforgeeks.org" in i['href']):

    # call get method to request next url
    nextpage = requests.get(i['href'])

    # create soup for next url
    nextsoup = BeautifulSoup(nextpage.content, 'html.parser')

    # we can scrap any thing of the
    # next page here we are scraping title of 
    # nexturl page string
    print("next url title : ",nextsoup.find('title').string)
```

**以下是全部实现:**

## 蟒蛇 3

```py
from bs4 import BeautifulSoup
import requests

# sample website
sample_website='https://www.geeksforgeeks.org/different-ways-to-remove-all-the-digits-from-string-in-java/'

# call get method to request the page
page=requests.get(sample_website)

# with the help of BeautifulSoup
# method and html parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

# With the help of find_all
# method perform searching in parser tree
for i in soup.find_all('a', href = True):

  # check all link which is contain
  # "www.geeksforgeeks.org" string 
  if("www.geeksforgeeks.org" in i['href']):

    # call get method to request next url
    nextpage = requests.get(i['href'])

    # create soup for next url
    nextsoup = BeautifulSoup(nextpage.content, 'html.parser')

    # we can scrap any thing of the
    # next page here we are scraping title of 
    # nexturl page string
    print("next url title : ",nextsoup.find('title').string)
```

**输出:**

```py
next url title :  GeeksforGeeks | A computer science portal for geeks
next url title :  Analysis of Algorithms | Set 1 (Asymptotic Analysis) - GeeksforGeeks
next url title :  Analysis of Algorithms | Set 2 (Worst, Average and Best Cases) - GeeksforGeeks
next url title :  Analysis of Algorithms | Set 3 (Asymptotic Notations) - GeeksforGeeks
next url title :  Analysis of algorithms | little o and little omega notations - GeeksforGeeks
next url title :  Lower and Upper Bound Theory - GeeksforGeeks
next url title :  Analysis of Algorithms | Set 4 (Analysis of Loops) - GeeksforGeeks
next url title :  Analysis of Algorithm | Set 4 (Solving Recurrences) - GeeksforGeeks
next url title :  Analysis of Algorithm | Set 5 (Amortized Analysis Introduction) - GeeksforGeeks
next url title :  What does 'Space Complexity' mean? - GeeksforGeeks
next url title :  Pseudo-polynomial Algorithms - GeeksforGeeks
next url title :  Polynomial Time Approximation Scheme - GeeksforGeeks
next url title :  A Time Complexity Question - GeeksforGeeks
................................................................. 
```