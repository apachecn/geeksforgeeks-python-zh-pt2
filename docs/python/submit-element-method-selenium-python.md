# 提交()元素法–硒蟒

> 原文:[https://www . geesforgeks . org/submit-element-method-selenium-python/](https://www.geeksforgeeks.org/submit-element-method-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。要使用硒 Python 打开网页，请使用 get 方法-硒 Python 签出–[导航链接。仅仅能够去一些地方并没有多大用处。我们真正想做的是与页面交互，或者更具体地说，与页面中的 HTML 元素交互。使用硒元素有多种策略，结账–](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python/)[定位策略](https://www.geeksforgeeks.org/locator-strategies-selenium-python/)

本文围绕如何在硒中使用`submit`方法展开。`submit`方法用于在将数据发送到表单后提交表单。

**Syntax –**

```
element.submit()
```

**示例–**

```
<input type="text" name="passwd" id="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
element = driver.find_element_by_xpath("//input[@id='passwd-id']")
```

此外，要找到多个元素，我们可以使用–

```
elements = driver.find_elements_by_name("passwd")
```

例如，要在字段中输入文本，

```
element.send_keys("some text")
```

现在，您可以使用提交此搜索

```
element.submit()
```

## Selenium Python 中如何使用提交元素方法？

让我们尝试在 geeksforgeeks 上的搜索栏中输入文本，然后提交其内容。
**节目–**

```
# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element 
element = driver.find_element_by_id("gsc-i-id2")

# send keys 
element.send_keys("Arrays")

# submit contents
element.submit()
```

**输出-**

![clear element method - Selenium Python](img/f064e7f56f429846a660c5a31e94c214.png)