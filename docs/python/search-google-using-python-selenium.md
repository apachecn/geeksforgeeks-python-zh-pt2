# 使用 Python Selenium 搜索谷歌

> 原文:[https://www . geesforgeks . org/search-Google-using-python-selenium/](https://www.geeksforgeeks.org/search-google-using-python-selenium/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。通过硒 Python 应用编程接口，您可以直观地访问硒网络驱动程序的所有功能。本文说明了如何使用 Selenium Python 编写第一个使用 Selenium 的程序来使用 Python Selenium 搜索 Google。

如果您还没有安装 Selenium 及其组件，请从这里开始安装–[Selenium Python 介绍和安装](https://contribute.geeksforgeeks.org/?p=1627739&preview=true)。

## 如何使用 Python Selenium 搜索谷歌

谷歌搜索有一个网址，你可以在那里添加你的关键词，它会为你搜索关键词。比如–**"https://google.co.in/search？q=gfg"** ，这将在 google.co.in .上搜索 gfg，以同样的方式，我们任意提供我们想要搜索的关键词或从用户那里获取输入。这是一个理解 Selenium 工作原理的示例程序。

安装完 Selenium 后，创建一个名为 run . py as–
**Program–**的文件

```py
# Python program to demonstrate
# selenium

# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# enter keyword to search
keyword = "geeksforgeeks"

# get google.co.in
driver.get("https://google.co.in / search?q ="+keyword)
```

**输出-**

![search-google-using-python-selenium](img/68f75ce944d9358c6c6fa071c2fd2345.png)