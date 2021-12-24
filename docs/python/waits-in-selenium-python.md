# 在硒蟒中等待

> 原文:[https://www.geeksforgeeks.org/waits-in-selenium-python/](https://www.geeksforgeeks.org/waits-in-selenium-python/)

硒 Python 是测试自动化的伟大工具之一。如今，大多数网络应用程序都在使用 AJAX 技术。当浏览器加载一个页面时，该页面中的元素可能会以不同的时间间隔加载。这使得定位元素变得困难:如果一个元素还没有出现在 DOM 中，定位函数将会引发 ElementNotVisibleException 异常。使用等待，我们可以解决这个问题。等待在执行的操作之间提供了一定的间隔，主要是定位元素或元素的任何其他操作。硒网络驱动程序提供两种类型的等待–

*   [隐式等待](#implicit)
*   [明确等待](#explicit)

## 隐式等待

隐式等待告诉网络驱动程序在试图找到任何不立即可用的元素时轮询 DOM 一段时间。默认设置为 0。一旦设置，隐式等待将在 WebDriver 对象的生命周期内设置。让我们考虑一个例子–

```py
# import webdriver
from selenium import webdriver

driver = webdriver.Firefox()

# set implicit wait time
driver.implicitly_wait(10) # seconds

# get url
driver.get("http://somedomain / url_that_delays_loading")

# get element after 10 seconds
myDynamicElement = driver.find_element_by_id("myDynamicElement")
```

这将在引发超时异常之前等待 10 秒钟，除非它发现元素在 10 秒钟内返回。要查看如何在网络驱动程序中实际实现隐式等待，请在上查看硒蟒中的[隐式等待](https://www.geeksforgeeks.org/implicit-waits-in-selenium-python/)

## 显式等待

显式等待是您定义的代码，用于在继续执行代码之前等待特定条件的出现。这种情况的极端情况是 time.sleep()，它将条件设置为等待的确切时间段。提供了一些方便的方法来帮助您编写只等待所需时间的代码。显式等待是通过结合使用 webdriverWait 类和 expected_conditions 实现的。让我们考虑一个例子–

```py
# import necessary classes
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

# create driver object 
driver = webdriver.Firefox()

# A URL that delays loading
driver.get("http://somedomain / url_that_delays_loading")

try:
    # wait 10 seconds before looking for element
    element = WebDriverWait(driver, 10).until(
        EC.presence_of_element_located((By.ID, "myDynamicElement"))
    )
finally:
    # else quit
    driver.quit()
```

这将在引发超时异常之前等待 10 秒钟，除非它发现元素在 10 秒钟内返回。默认情况下，WebDriverWait 每 500 毫秒调用一次 ExpectedCondition，直到它成功返回。
**预期条件–**
在自动化网络浏览器时，有一些常用的条件。例如，presence_of_element_located、title_is、ad 等等。您可以从这里查看整个方法–[便利方法](https://selenium-python.readthedocs.io/api.html#module-selenium.webdriver.support.expected_conditions)。其中一些是–

*   标题列表
*   标题 _ 包含
*   已定位元素的存在
*   定位元素的可见性
*   的可见性
*   存在所有已定位的元素
*   元素 _ 定位 _ 待选
*   元素选择状态目标
*   元素定位选择状态目标
*   alert_is_present

要查看如何在网络驱动程序中实际实现隐式等待，请查看硒 Python 中的[显式等待](https://www.geeksforgeeks.org/explicit-waits-in-selenium-python/)