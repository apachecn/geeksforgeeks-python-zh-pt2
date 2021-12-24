# PYqt5 QDockWidget–顶级更改信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-顶层-已更改-信号/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-top-level-changed-signal/)

在本文中，我们将看到如何获得 QDockWidget 的顶层变化信号。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。当浮动属性改变时，会发出此信号。
如果 dock 小部件现在浮动，则 topLevel 参数为真；否则，就是假的。

> 为此，我们将对 dock widget 对象使用`topLevelChanged`方法。
> 
> **语法:**dock . toplevelchanged . connect(方法)
> 
> **自变量:**以方法为自变量
> 
> **返回:**返回无

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

        # getting top level changed changed signal
        # setting text to the label
        dock.topLevelChanged.connect(lambda: label.setText("Top level Changed Signal Emitted"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-459988-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200725013208/Python-2020-07-25-01-30-55.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200725013208/Python-2020-07-25-01-30-55.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200725013208/Python-2020-07-25-01-30-55.mp4)</video>