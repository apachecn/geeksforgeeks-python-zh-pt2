# PyQt5 QDockWidget–设置其功能

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-setting-features-of-it/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-features-of-it/)

在本文中，我们将看到如何为 QDockWidget 设置特性。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。

坞站已经启用了许多功能，还有可移动、可关闭、可浮动、水平标题栏等功能，或者可以选择设置所有功能或不设置任何功能。

> 为此，我们将对 dock widget 对象使用`setFeatures`方法。
> 
> **语法:**dock . set features(qdlock widget)。DockWidgetClosable)
> 
> **自变量:**以特征为自变量
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
        dock = QDockWidget("GeeksforGeeks", self)

        # push button
        push = QPushButton("Press", self)

        # setting widget to the dock
        dock.setWidget(push)

        # setting feature to the dock
        dock.setFeatures(QDockWidget.DockWidgetClosable)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-458942-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200724002336/Python-2020-07-24-00-23-04.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200724002336/Python-2020-07-24-00-23-04.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200724002336/Python-2020-07-24-00-23-04.mp4)</video>