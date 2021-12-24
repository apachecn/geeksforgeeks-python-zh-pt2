# 从动态网站上抓取内容

> 原文:[https://www . geesforgeks . org/scratch-content-from-dynamic-sites/](https://www.geeksforgeeks.org/scrape-content-from-dynamic-websites/)

为了从一个静态页面中抓取内容，我们使用了美丽组作为我们的抓取包，它可以完美地用于静态页面。我们使用请求将页面加载到 python 脚本中。现在，如果我们试图加载的页面本质上是动态的，并且我们通过请求库请求这个页面，那么它将发送要在本地执行的 JS 代码。Requests 包不执行这个 JS 代码，只是把它作为页面源。

美丽组没有捕捉到通过 Java 脚本与 DOM 的交互。让我们假设，如果您有一个由 JS 生成的表。美丽组将无法捕获它，而硒可以。

如果只是需要刮擦静态网站，我们会只使用 bs4。但是，对于动态生成的网页，我们使用硒。
**硒**

Selenium 是一个免费(开源)的自动化测试框架，用于跨不同浏览器和平台验证 web 应用程序。您可以使用多种编程语言，如 Java、C#、Python 等来创建 Selenium 测试脚本。这里，我们使用 Python 作为我们的主要语言。

首先，安装:

**1)python 中的硒绑定**

```py
pip install selenium

```

**2)网络驱动**
Selenium 需要一个网络驱动与选择的浏览器进行交互。Web 驱动程序是一个与 web 浏览器交互的包。它通过通用的有线协议与网络浏览器或远程网络服务器进行交互。您可以签出并安装您选择的网络驱动程序。

```py
Chrome: https://sites.google.com/a/chromium.org/chromedriver/downloads
Firefox: https://github.com/mozilla/geckodriver/releases
Safari:    https://webkit.org/blog/6900/webdriver-support-in-safari-10/ 

```

**美丽的脉冲星**

是一个 Python 库，用于从 HTML 和 XML 文件中提取数据。它与您最喜欢的解析器一起工作，提供导航、搜索和修改解析树的惯用方式。它通常可以节省程序员数小时或数天的工作。

为了使用美丽的汤，我们在 python 中有这个奇妙的绑定:
**1)在 python 中的 BS4 绑定**

```py
pip install bs4

```

让我们假设站点是动态的，简单的抓取导致返回一个非类型对象。

```py
#### This program scrapes naukri.com's page and gives our result as a 
#### list of all the job_profiles which are currently present there. 

import requests
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time

#url of the page we want to scrape
url = "https://www.naukri.com/top-jobs-by-designations# desigtop600"

# initiating the webdriver. Parameter includes the path of the webdriver.
driver = webdriver.Chrome('./chromedriver') 
driver.get(url) 

# this is just to ensure that the page is loaded
time.sleep(5) 

html = driver.page_source

# this renders the JS code and stores all
# of the information in static HTML code.

# Now, we could simply apply bs4 to html variable
soup = BeautifulSoup(html, "html.parser")
all_divs = soup.find('div', {'id' : 'nameSearch'})
job_profiles = all_divs.find_all('a')

# printing top ten job profiles
count = 0
for job_profile in job_profiles :
    print(job_profile.text)
    count = count + 1
    if(count == 10) :
        break

driver.close() # closing the webdriver
```

下面是铲运机在行动的视频:[工作 _ 铲运机 _ 视频](https://media.geeksforgeeks.org/wp-content/uploads/20200627101616/working_scraper.wmv)

**代码输出:**

![](img/758c4327fd8333ce03ddf86c54ca2511.png)