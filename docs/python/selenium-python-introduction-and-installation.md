# 硒蟒介绍及安装

> 原文:[https://www . geesforgeks . org/selenium-python-introduction-and-installation/](https://www.geeksforgeeks.org/selenium-python-introduction-and-installation/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。通过硒 Python 应用编程接口，您可以直观地访问硒网络驱动程序的所有功能。要查看更多关于硒的详细信息，请访问–[硒基础知识–组件、特性、用途和限制](https://geeksforgeeks.org/selenium-basics-components-features-uses-and-limitations/)。

## 硒蟒游戏攻略

硒 Python 绑定提供了一个方便的应用编程接口来访问硒网络驱动程序，如火狐、Ie、Chrome、远程等。目前支持的 Python 版本有 2.7、3.5 及以上版本。

*   **开源可移植**–Selenium 是一个开源可移植的 Web 测试框架。
*   **工具和 DSL 的结合**–Selenium 是工具和 DSL(领域特定语言)的结合，以进行各种类型的测试。
*   **更容易理解和实现**–Selenium 命令按照不同的类进行分类，这样更容易理解和实现。
*   **减少测试执行时间**–Selenium 支持并行测试执行，减少执行并行测试所花费的时间。
*   **所需资源更少**–与 UFT、RFT 等竞争对手相比，Selenium 所需资源更少。
*   **支持多种操作系统**–安卓、iOS、Windows、Linux、Mac、Solaris。
*   **支持多浏览器**–谷歌 Chrome、Mozilla Firefox、Internet Explorer、Edge、Opera、Safari 等。
*   **并行测试执行**–它还支持并行测试执行，减少了时间，提高了测试效率。

## 硒蟒安装

对于任何操作系统，在操作系统上安装 python 之后，都可以安装 selenium。如果没有，请结帐–[下载并安装 Python 3 最新版本](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)

**第一种方法**
打开终端/Cmd，写下如下命令

```
python -m pip install selenium
```

**第二种方法**
或者，你可以在这里下载源码发布[，将其取消归档，运行下面的命令:](https://pypi.python.org/pypi/selenium)

```
python setup.py install
```

#### 安装网络驱动程序

一个人可以安装火狐、Chromium、PhantomJs(现已弃用)等。

*   要使用火狐，你可能需要安装 GeckoDriver
*   要使用 Chrome，您可能需要安装 Chrome

在本文中，使用了火狐，因此可以按照以下步骤进行安装:-

【Linux 的步骤:-
1。转到[壁虎释放页面](https://github.com/mozilla/geckodriver/releases)。为您的平台找到最新版本的驱动程序并下载。
例如:

```
wget https://github.com/mozilla/geckodriver/releases/download/v0.24.0/geckodriver-v0.24.0-linux64.tar.gz
```

2.使用以下命令提取文件:

```
tar -xvzf geckodriver*
```

3.使其可执行:

```
chmod +x geckodriver
```

4.将文件移动到 usr/local/bin

```
sudo mv geckodriver /usr/local/bin/
```

【Windows 的步骤:-
1。与 Linux 中的步骤 1 相同下载[壁虎河](https://github.com/mozilla/geckodriver/releases)T5【2】。使用 WinRar 或您可能拥有的任何应用程序提取它。
3。使用命令提示符将其添加到路径中

```
setx path "%path%;GeckoDriver Path"
```

例如:-

```
setx path "%path%;c:/user/eliote/Desktop/geckodriver-v0.26.0-win64/geckodriver.exe"
```

#### 创建简单代码

## 蟒蛇 3

```
# Python program to demonstrate
# selenium

# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()
# get google.co.in
driver.get("https://google.co.in")
```

**输出:**

![python-selenium](img/31ac1e88432a086a9fb1e046c67532d7.png)