# 使用 Python 在 Selenium 中向前()和向后()的网络驱动程序导航命令

> 原文:[https://www . geesforgeks . org/web driver-navigative-commands-前向和后向-in-selenium-with-python/](https://www.geeksforgeeks.org/webdriver-navigational-commands-forward-and-backward-in-selenium-with-python/)

硒是通过程序控制互联网浏览器的有效设备。它对所有浏览器都是有目的的，适用于所有基本操作系统，其脚本是用许多语言编写的，如 Python、Java、C#等，我们可以用 Python 运行。

**要求:**需要安装 chromedriver 并设置路径。[点击此处](https://sites.google.com/a/chromium.org/chromedriver/downloads)下载，更多信息请点击[此链接](https://www.geeksforgeeks.org/browser-automation-using-selenium/)。

**网络驱动导航命令:**

1.  **forward():** 根据浏览器历史将我们带到下一页
2.  **back():** 按照浏览器历史将我们带到上一页

**程序:**

1.  导入模块
2.  创建一个 Chrome 实例。
3.  进入第一个网址
4.  显示页面标题。
5.  转到第二个网址
6.  显示页面标题。
7.  转到上一页并显示标题。
8.  转到下一页并显示标题。

**实施:**

## 蟒蛇 3

```
# importing the modules
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time

# using chrome driver
driver = webdriver.Chrome()

# taking first url
driver.get("https://www.geeksforgeeks.org/")
# getting title
print(driver.title)

# taking 2nd url
driver.get("https://www.youtube.com/")
# getting the title
print(driver.title)

# given time open url
time.sleep(2)

# WebDriver Navigational Commands backward
driver.back()
# given time open url
time.sleep(2)
# if back then given previous title
print(driver.title)

# WebDriver Navigational Commands backward
driver.forward()
# given time open url
time.sleep(2)
# if goto forward then given next title
print(driver.title)

driver.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-491101-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200922194307/22.09.2020_19.33.53_REC.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200922194307/22.09.2020_19.33.53_REC.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200922194307/22.09.2020_19.33.53_REC.mp4)</video>