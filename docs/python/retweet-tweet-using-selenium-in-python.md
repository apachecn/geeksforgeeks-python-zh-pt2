# 使用 Python 中的硒转发推文

> 原文:[https://www . geesforgeks . org/retweet-tweet-using-selenium in-python/](https://www.geeksforgeeks.org/retweet-tweet-using-selenium-in-python/)

**先决条件:**

*   [硒网络驱动](https://www.geeksforgeeks.org/browser-automation-using-selenium/)。
*   [网络驱动方法](https://www.geeksforgeeks.org/web-driver-methods-in-selenium-python/)
*   [定位网页中元素的方法](https://www.geeksforgeeks.org/locating-multiple-elements-in-selenium-python/)

在本文中，我们将看到如何为特定的标签转发，并决定它是否会显示在推特的趋势部分。我们可以让推特上的一个账户自动转发与任何特定标签相关的所有推文。这可以使用 Python 中的 Selenium 来实现。

**注意:**可以在[这里](https://chromedriver.chromium.org/downloads)下载网络驱动。

### **分步实施:**

**步骤 1:** 导入所需模块

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.support.ui import WebDriverWait
import time
from selenium.common.exceptions import NoSuchElementException
from selenium.common.exceptions import ElementClickInterceptedException
from selenium.common.exceptions import StaleElementReferenceException
from selenium.webdriver.common.keys import Keys
from selenium.webdriver import ActionChains
import getpass
```

**步骤 2** 执行网络驱动程序，并将其分配给变量驱动程序。

## 蟒蛇 3

```
driver = webdriver.Chrome(executable_path='/usr/lib/chromium-browser/chromedriver')
```

**第三步:**指向所需的网址，使用[最大化窗口](https://www.geeksforgeeks.org/maximize_window-driver-method-selenium-python/)最大化窗口。

## 蟒蛇 3

```
driver.get('https://twitter.com/login')
driver.maximize_window()
```