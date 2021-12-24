# PYqt5 QDockWidget–获取允许区域

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-allowed-areas/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-allowed-areas/)

在本文中，我们将看到如何获得 QDockWidget 的允许区域。QDockWidget 提供了 dock widgets 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。Dock 可以在主窗口的任何地方移动，设置 dock widget 可以放置的允许区域，可以借助`setAllowedAreas`方法进行设置。

> 为此，我们将对 dock widget 对象使用`allowedAreas`方法。
> 
> **语法:** dock.allowedAreas()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QDockWidgetArea 对象

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating dock widget
        dock = QDockWidget("GeeksforGeeks", self)

        # push button
        push = QPushButton("Press", self)

        # setting widget to the dock
        dock.setWidget(push)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # getting allowed areas of the dock
        value = dock.allowedAreas()

        # setting text to the label
        label.setText("Allowed Areas : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8b9c78b2a8d5265c3bf9781a5c6184db.png)