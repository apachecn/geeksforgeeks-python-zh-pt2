# PyQt5 QDockWidget–检查浮动属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-checking-floating-property/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-checking-floating-property/)

在本文中，我们将看到如何检查 QDockWidget 的浮动属性是否已启用。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。此属性保存 dock 小部件是否浮动。
浮动停靠小部件作为其父 QMainWindow“之上”的独立窗口呈现给用户，而不是停靠在 QMainWindow 中，可以借助`setFloating`方法进行设置。

> 为此，我们将对 dock widget 对象使用`isFloating`方法。
> 
> **语法:** dock.isFloating()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # checking floating property
        value = dock.isFloating()

        # setting text to the label
        label.setText("Is Floating : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/89fb0f8a37a8afec49efcc2ae6821db5.png)