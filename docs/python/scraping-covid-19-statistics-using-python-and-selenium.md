# 用 Python 和 Selenium 刮新冠肺炎统计

> 原文:[https://www . geeksforgeeks . org/scratch-新冠肺炎-统计-使用-python-and-selenium/](https://www.geeksforgeeks.org/scraping-covid-19-statistics-using-python-and-selenium/)

Selenium 是一个开源的 web 测试工具，允许用户跨不同的浏览器和平台测试 web 应用。它包含了开发人员可以用来自动化网络应用程序的大量软件，包括 IDE、RC、网络驱动程序和 Selenium grid，它们都服务于不同的目的。而且，它服务于抓取动态网页的目的，这是美汤做不到的。

**1。蟒蛇中的<u>硒绑定</u>**

硒 Python 绑定提供了一个简单的应用编程接口来使用它的网络驱动程序编写功能测试。通过应用编程接口，您可以轻松访问 Selenium 网络驱动程序的所有功能。

```
pip install Selenium

```

**1。B <u>网络驱动</u>**

Selenium 需要一个 web 驱动来与选择的浏览器，即 Chrome、Safari、Firefox 等进行接口和交互。web 驱动程序是一个用来设置与用户的 web 浏览器交互的包。它通过通用的有线协议进行交互。

可以轻松安装与浏览器兼容的网页驱动。以下链接将帮助您做到这一点:

<figure class="table">

| **铬**: | [https://sites . Google . com/a/chromium . org/chrome driver/downloads](https://sites.google.com/a/chromium.org/chromedriver/downloads) |
| **边缘**: | [https://developer . Microsoft . com/en-us/Microsoft-edge/tools/web driver/](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/) |
| **Firefox** : | [https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases) |
| **Safari** : | [https://web kit . org/blog/6900/web driver-support-in-safari-10/](https://webkit.org/blog/6900/webdriver-support-in-safari-10/) |

</figure>

**2。一<u>使用 Python 绑定</u>**

如果你已经安装了 Selenium Python 绑定，可以像这样从 Python 开始使用:

```
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from time import sleep

```

睡眠模块等待，直到浏览器网址已经完全加载。现在我们创建一个浏览器 webdriver 实例(这里是 Chrome)，如下所示:

```
driver=webdriver.Chrome("C:/chromedriver.exe")
driver.get("https://www.covid19india.org/")
sleep(2) //Waits for 2 seconds after navigating to the URL

```

**driver.get()** 方法导航到由网址给定的页面，然后 chromedriver 等待直到页面完全加载，然后将控制权返回给脚本。

**2。乙<u>刮网</u>T3】**

在页面中定位元素有多种策略。在这种情况下，我们使用 **find_element_by_xpath()** 方法在***【https://www.covid19india.org/.】***上导航到所需的 HTML 渲染值。上面的脚本从所需的 URL 中提取了七个不同的值，即:

*   *Total number of cases*
*   *Total active cases*
*   *Total number of recovered cases*
*   *Total number of deaths*

这些提取的新冠肺炎统计值使用 Python 使用 **print()** 语句实时显示在用户控制台上，如下所示:

```
***def extractor():***

 ***TCases = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[1]/h1/span")*** 
 ***TActive = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[2]/h1/span")*** 
 ***TRecov = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[3]/h1/span")*** 
 ***TDeath = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[4]/h1/span")*** 
 ***New_Cases = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[1]/h4/span")*** 
 ***New_Rcov = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[3]/h4/span")*** 
 ***New_Death = driver.find_element_by_xpath("/html/body/div/div/div[2]/div[1]/div[2]/div[4]/h4/span")***
            ***print("Total Cases:", TCases.text)***
    ***print("Total Active Cases:", TActive.text)***
    ***print("Total Recovered Cases:", TRecov.text)***
    ***print("Total Deaths:", TDeath.text)***
    ***print("New Cases:", New_Cases.text[1:len(New_Cases.text)-1])***
    ***print("New Recovered Cases:", New_Rcov.text[1:len(New_Rcov.text)-1])***
    ***print("Additional Deaths yet:", New_Death.text[1:len(New_Death.text)-1])***

```

使用 **sleep()** 模块，整个脚本可以在给定的时间间隔后自动执行，如下所示:

```
***while True:***
 ***extractor()***
 ***sleep(60*60)   // The loop executes after every hour in this case***

```

while 循环无限期执行，每小时运行一次**提取器()**功能。

以下是整个网页抓取程序:

```
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from time import sleep

driver = webdriver.Chrome("C:/chromedriver.exe")
driver.get("https://www.covid19india.org/")
sleep(2)

def extractor():
    TCases = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[1]/h1 / span")
    TActive = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[2]/h1 / span")
    TRecov = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[3]/h1 / span")
    TDeath = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[4]/h1 / span")
    New_Cases = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[1]/h4 / span")
    New_Rcov = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[3]/h4 / span")
    New_Death = driver.find_element_by_xpath(
        "/html / body / div / div / div[2]/div[1]/div[2]/div[4]/h4 / span")

    print("Total Cases:", TCases.text)
    print("Total Active Cases:", TActive.text)
    print("Total Recovered Cases:", TRecov.text)
    print("Total Deaths:", TDeath.text)
    print("New Cases:", New_Cases.text[1:len(New_Cases.text)-1])
    print("New Recovered Cases:", New_Rcov.text[1:len(New_Rcov.text)-1])
    print("Additional Deaths yet:", New_Death.text[1:len(New_Death.text)-1])

while True:
    extractor()
    sleep(60 * 60)
```

上述程序在用户控制台上的输出如下:

```
***Total Cases: 2, 17, 187*** 
***Total Active Cases: 1, 07, 017*** 
***Total Recovered Cases: 1, 04, 071*** 
***Total Deaths: 6, 088*** 
***New Cases: +2561***
***New Recovered Cases: +543***
***Additional Deaths yet: +23***
//The above COVID-19 values differ with time. Your output may differ. 
```

因此，上述脚本使用 Selenium 自动进行网页抓取，并每小时在用户控制台上打印更新的统计数据。

使用这个你可以为每个网站创建一个自定义的自动脚本，它可以自动执行你的所有操作。老实说，网页抓取和自动化没有限制，以上只是一个让你前进的例子。