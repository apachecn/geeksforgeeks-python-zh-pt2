# PYqt5 QDockWidget–获取布局

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-layout/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-layout/)

在本文中，我们将看到如何将布局应用到 QDockWidget。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。布局指定内部组件将如何排列我们可以设置，可以借助`setLayout`方法进行设置。

> 为此，我们将对 dock widget 对象使用`layout`方法。
> 
> **语法:** dock.layout()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QLayout 对象

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

        # getting layout of dock
        value = dock.layout()

        # setting text to the label
        label.setText("Layout : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5e2c30ea7cd37f3f65cff58f4dcbfd84.png)