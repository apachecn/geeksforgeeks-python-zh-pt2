# PYqt5 QDockWidget–设置允许区域

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-设置-允许-区域/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-allowed-areas/)

在本文中，我们将看到如何为 QDockWidget 设置允许的区域。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。Dock 可以移动到主窗口中的任何位置，设置 dock 小部件可以放置的允许区域。

> 为此，我们将对 dock widget 对象使用`setAllowedAreas`方法。
> 
> **语法:** dock.setAllowedAreas(区域)
> 
> **参数:**它以 QDockWidgetArea 对象为参数
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

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # setting allowed areas
        dock.setAllowedAreas(Qt.AllDockWidgetAreas)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-458950-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200724005711/Python-2020-07-24-00-56-52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200724005711/Python-2020-07-24-00-56-52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200724005711/Python-2020-07-24-00-56-52.mp4)</video>