# PYqt5 QDockWidget–设置窗口标题属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-设置-窗口-标题-属性/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-window-title-property/)

在本文中，我们将看到如何设置 QDockWidget 的窗口标题。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。此属性保存 dock 小部件标题(标题)。
默认情况下，该属性包含一个空字符串。该标题出现在 dock 小部件窗口的顶部。

> 为此，我们将对 dock widget 对象使用`setWindowTitle`方法。
> 
> **语法 ：** dock.setWindowTitle（标题）
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

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
        dock = QDockWidget(self)

        # setting title to the doc widget
        dock.setWindowTitle("GfG Dock")

        # push button
        push = QPushButton("Press", self)

        # setting floating property
        dock.setFloating(False)

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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/7a71f7515c35477c97c2ae223b6dfdcd.png)