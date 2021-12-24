# PyQt5 QDockWidget–从中获取功能

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-features-from-it/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-features-from-it/)

在本文中，我们将看到如何获得 QDockWidget 的特性。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。
坞站已经启用了许多功能，也有可移动、可关闭、可浮动、水平标题栏等功能，或者有设置所有功能或不设置功能的选项，这些都可以借助`setFeatures`方法进行设置。

> 为此，我们将对 dock widget 对象使用`features`方法。
> 
> **语法:** dock.features()
> 
> **论证:**不需要论证
> 
> **返回:**返回特征对象

下面是实现

```
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

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting features of the dock
        value = dock.features()

        # setting text to the label
        label.setText("Features : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/3a3baa1b380f0b33ec96f62bd8f27ef6.png)