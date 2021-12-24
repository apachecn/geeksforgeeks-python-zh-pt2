# 基于关键词和区域提取邮件的网页抓取器

> 原文:[https://www . geeksforgeeks . org/web-scratcher-for-extracting-emails-基于关键字和区域/](https://www.geeksforgeeks.org/web-scraper-for-extracting-emails-based-on-keywords-and-regions/)

**网页抓取**是一项任务，通常是从网站上抓取结构化数据，然后相应地存储起来，这种数据的价值足以打开各种领域的大门，从数据挖掘相关的东西到数据科学相关的应用程序，在这些应用程序中需要大量数据来做出商业决策。

至于这篇文章，我们将讨论如何使用网页抓取器根据关键词和位置提取电子邮件。

所以问题来了，为什么我们需要这样的东西？嗯，基于特定主题和地区提取的电子邮件可以是一种非常有效的广告和产品推广方式，尽管有人会说这可以用于黑帽搜索引擎优化，这实际上取决于你如何使用它。

### 要求:

*   **Scrapy 模块:**用作 web 报废的 Python 框架。从普通网站获取数据更容易，只需要拉取网站的 HTML，通过过滤标签获取数据就可以实现。可以使用下面的命令安装它。

```
pip install scrapy
```

*   **硒模块:**是通过程序控制网页浏览器的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等。可以使用下面的命令安装它。

```
pip install selenium
```

*   **Scrapy-Selenium 模块:**它是一个 *scrapy* 中间件，使用 *selenium* 处理 JavaScript 页面。可以使用下面的命令安装它。

```
pip install scrapy-selenium
```

*   **谷歌模块:**使用 python 包*谷歌*我们可以从一个 python 脚本中得到谷歌搜索的结果。可以使用下面的命令安装它。

```
pip install google
```

### 逐步方法:

**步骤 1:** 使用以下命令创建剪贴簿项目:

```
scrapy startproject email_extraction
```

执行上述命令后，您将看到一个文件夹，其树如下所示

```
├── email_extraction
│   ├── __init__.py
│   ├── items.py
│   ├── middlewares.py
│   ├── pipelines.py
│   ├── __pycache__
│   ├── settings.py
│   └── spiders
│       ├── email_extractor.py
│       ├── __init__.py
│       └── __pycache__
└── scrapy.cfg

4 directories, 8 files
```

在*蜘蛛*目录中创建一个 python 文件，并在任何编辑器中打开它。

**步骤 2:** 导入所需的库

## 蟒蛇 3

```
# import required modules
import scrapy
from scrapy.spiders import CrawlSpider, Request
from googlesearch import search
import re
from scrapy_selenium import SeleniumRequest
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
```

现在所需的库已经导入，我们可以进入脚本的下一步。

**步骤 3:** 设置爬虫所需的参数

## 蟒蛇 3

```
# create class to extract email ids
class email_extractor(CrawlSpider):

    # adjusting parameters
    name = 'email_ex'

    def __init__(self, *args, **kwargs):
        super(email_extractor, self).__init__(*args, **kwargs)
        self.email_list = []
        self.query = " 'market places'.gmail.com "
```