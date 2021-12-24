# 使用 PyQt5

创建一个简单的浏览器

> 原文:[https://www . geeksforgeeks . org/creating-a-simple-browser-use-pyqt 5/](https://www.geeksforgeeks.org/creating-a-simple-browser-using-pyqt5/)

在本文中，我们将看到如何使用 PyQt5 创建一个简单的浏览器。

**网络浏览器**是用于访问万维网上的信息的软件应用程序。当用户从特定网站请求网页时，网络浏览器从网络服务器检索必要的内容，然后在屏幕上显示该网页。

**PyQt5** 是跨平台的 GUI 工具包，一套针对 Qt v5 的 python 绑定。由于该库提供的工具和简单性，人们可以非常容易地开发交互式桌面应用程序。

> **GUI 实现步骤:**
> 1。创建主窗口
> 2。创建一个 QWebEngineView 对象，并将其作为中心小部件添加到主窗口
> 3。将状态栏添加到主窗口
> 4。创建一个工具栏，添加导航按钮和线编辑来显示网址，下面是热工具栏的样子
> 
> ![](img/90e7fcf050289813b6b9c9927db13f28.png)
> 
> **后端实现步骤:**
> 1。当 url 更改时，向 QWebEngineView 对象添加更新 url 操作。
> 2。在更新网址动作中改变网址栏的网址并改变光标位置
> 3。加载完成后，向 QWebEngineView 对象添加另一个更新标题动作
> 4。在更新标题方法中，将窗口标题更新为页面标题
> 5。使用 QWebEngineView 对象的内置功能为导航按钮添加动作，用于重载、后退、停止和前进按钮
> 6。将动作添加到主页按钮，并在动作内将 url 更改为 google.com
> 7。按下回车键
> 8 时，在线编辑中添加动作。在行编辑操作中，获取文本并将该文本转换为 QUrl 对象，如果该文本为空，则设置方案，并将该 Url 设置为 QWebEngineView 对象

下面是实现

## 蟒蛇 3

```py
# importing required libraries
from PyQt5.QtCore import *
from PyQt5.QtWidgets import *
from PyQt5.QtGui import *
from PyQt5.QtWebEngineWidgets import *
from PyQt5.QtPrintSupport import *
import os
import sys

# creating main window class
class MainWindow(QMainWindow):

    # constructor
    def __init__(self, *args, **kwargs):
        super(MainWindow, self).__init__(*args, **kwargs)

        # creating a QWebEngineView
        self.browser = QWebEngineView()

        # setting default browser url as google
        self.browser.setUrl(QUrl("http://google.com"))

        # adding action when url get changed
        self.browser.urlChanged.connect(self.update_urlbar)

        # adding action when loading is finished
        self.browser.loadFinished.connect(self.update_title)

        # set this browser as central widget or main window
        self.setCentralWidget(self.browser)

        # creating a status bar object
        self.status = QStatusBar()

        # adding status bar to the main window
        self.setStatusBar(self.status)

        # creating QToolBar for navigation
        navtb = QToolBar("Navigation")

        # adding this tool bar tot he main window
        self.addToolBar(navtb)

        # adding actions to the tool bar
        # creating a action for back
        back_btn = QAction("Back", self)

        # setting status tip
        back_btn.setStatusTip("Back to previous page")

        # adding action to the back button
        # making browser go back
        back_btn.triggered.connect(self.browser.back)

        # adding this action to tool bar
        navtb.addAction(back_btn)

        # similarly for forward action
        next_btn = QAction("Forward", self)
        next_btn.setStatusTip("Forward to next page")

        # adding action to the next button
        # making browser go forward
        next_btn.triggered.connect(self.browser.forward)
        navtb.addAction(next_btn)

        # similarly for reload action
        reload_btn = QAction("Reload", self)
        reload_btn.setStatusTip("Reload page")

        # adding action to the reload button
        # making browser to reload
        reload_btn.triggered.connect(self.browser.reload)
        navtb.addAction(reload_btn)

        # similarly for home action
        home_btn = QAction("Home", self)
        home_btn.setStatusTip("Go home")
        home_btn.triggered.connect(self.navigate_home)
        navtb.addAction(home_btn)

        # adding a separator in the tool bar
        navtb.addSeparator()

        # creating a line edit for the url
        self.urlbar = QLineEdit()

        # adding action when return key is pressed
        self.urlbar.returnPressed.connect(self.navigate_to_url)

        # adding this to the tool bar
        navtb.addWidget(self.urlbar)

        # adding stop action to the tool bar
        stop_btn = QAction("Stop", self)
        stop_btn.setStatusTip("Stop loading current page")

        # adding action to the stop button
        # making browser to stop
        stop_btn.triggered.connect(self.browser.stop)
        navtb.addAction(stop_btn)

        # showing all the components
        self.show()

    # method for updating the title of the window
    def update_title(self):
        title = self.browser.page().title()
        self.setWindowTitle("% s - Geek Browser" % title)

    # method called by the home action
    def navigate_home(self):

        # open the google
        self.browser.setUrl(QUrl("http://www.google.com"))

    # method called by the line edit when return key is pressed
    def navigate_to_url(self):

        # getting url and converting it to QUrl object
        q = QUrl(self.urlbar.text())

        # if url is scheme is blank
        if q.scheme() == "":
            # set url scheme to html
            q.setScheme("http")

        # set the url to the browser
        self.browser.setUrl(q)

    # method for updating url
    # this method is called by the QWebEngineView object
    def update_urlbar(self, q):

        # setting text to the url bar
        self.urlbar.setText(q.toString())

        # setting cursor position of the url bar
        self.urlbar.setCursorPosition(0)

# creating a pyQt5 application
app = QApplication(sys.argv)

# setting name to the application
app.setApplicationName("Geek Browser")

# creating a main window object
window = MainWindow()

# loop
app.exec_()
```

**输出:**

<video class="wp-video-shortcode" id="video-427477-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200606172102/Google-Geek-Browser-2020-06-06-17-20-27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200606172102/Google-Geek-Browser-2020-06-06-17-20-27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200606172102/Google-Geek-Browser-2020-06-06-17-20-27.mp4)</video>