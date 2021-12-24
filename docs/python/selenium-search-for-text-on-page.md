# 硒–在页面上搜索文本

> 原文:[https://www . geesforgeks . org/selenium-page-search-for-text-on-page/](https://www.geeksforgeeks.org/selenium-search-for-text-on-page/)

**先决条件:-** [硒](https://www.geeksforgeeks.org/selenium-python-tutorial/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

在本文中，我们将学习如何在 python 中使用 selenium 来知道文本是否在网页上。

**进场:**

*   首先，我们将使用**硒网驱动程序**中的 **chrome()** 方法打开 Chrome 驱动程序
*   分配**网址。**
*   然后**驱动**会打开【给 T2】网址
*   使用 **page_source** 属性获取网页源代码。
*   指定要搜索的文本。
*   获取网页文本后，我们将搜索文本是否存在。

**下面是实现:**

## 蟒蛇 3

```py
# import webdriver 
from selenium import webdriver

# create webdriver object 
driver = webdriver.Chrome()

# URL of the website 
url = "https://www.geeksforgeeks.org/"

# Opening the URL 
driver.get(url) 

# Getting current URL source code 
get_source = driver.page_source

# Text you want to search
search_text = "Floor"

# print True if text is present else False
print(search_text in get_source)
```

**输出:**

```py
True
```

**演示:**

<video class="wp-video-shortcode" id="video-566870-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210302181202/FreeOnlineScreenRecorderProject4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210302181202/FreeOnlineScreenRecorderProject4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210302181202/FreeOnlineScreenRecorderProject4.mp4)</video>