# 使用 Python 美化程序刮取谷歌搜索结果

> 原文:[https://www . geeksforgeeks . org/scrap-Google-search-results-use-python-beautulsoup/](https://www.geeksforgeeks.org/scrape-google-search-results-using-python-beautifulsoup/)

在本文中，我们将看到如何使用 Python 美化程序来抓取谷歌搜索结果。

### **所需模块:**

*   **bs4:** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install bs4

```

*   **请求:** Requests 可以让你极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install requests

```

### **进场:**

*   导入美丽的组和请求库。
*   用默认的谷歌搜索网址**'https://google.com/search 做两个字符串？q='** 和我们定制的搜索关键词。
*   连接这两个字符串来获得我们的搜索网址。
*   使用 **requests.get(url)获取 URL 数据，**将其存储在变量**requests _ result**中。
*   使用 **request_result.text.** ，创建一个字符串并存储我们获取的请求的结果
*   现在我们使用美丽的输出来分析提取的页面。我们可以简单地创建一个对象来执行这些操作，但是 beautifulsoup 附带了许多内置功能来抓取网页。我们已经创建了一个汤对象，首先使用请求-响应中的美丽组
*   我们可以做 **soup.find.all(h3)** 来抓取搜索结果的所有主要标题，遍历对象并将其打印为字符串。

**例 1:** 下面是上述方法的实现。

## 蟒 3

```py
# Import the beautifulsoup 
# and request libraries of python.
import requests
import bs4

# Make two strings with default google search URL
# 'https://google.com/search?q=' and
# our customized search keyword.
# Concatenate them
text= "geeksforgeeks"
url = 'https://google.com/search?q=' + text

# Fetch the URL data using requests.get(url),
# store it in a variable, request_result.
request_result=requests.get( url )

# Creating soup from the fetched request
soup = bs4.BeautifulSoup(request_result.text,
                         "html.parser")
print(soup)
```