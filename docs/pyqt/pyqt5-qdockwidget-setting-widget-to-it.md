# PyQt5 QDockWidget–将小部件设置为它

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-setting-widget-to-it/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-widget-to-it/)

在本文中，我们将看到如何将小部件设置为 QDockWidget。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。终端用户可以将停靠窗口移动到其当前区域内，移动到新的区域，并将其浮动(例如，取消停靠)。

我们可以将小部件添加到 dock 小部件中，小部件可以是任何小部件，甚至是包含许多子小部件的单个小部件。除了 dock 小部件，为其设置的小部件也会随之移动。

> 为此，我们将对 dock widget 对象使用`setWidget`方法。
> 
> **语法:** dock.setWidget(widget)
> 
> **自变量:**它以 QWidget 为自变量
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

        # adding action to the push button
        push.clicked.connect(lambda: label.setText("Dock Widget's Push button pressed"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-458939-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200724000825/Python-2020-07-24-00-07-55.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200724000825/Python-2020-07-24-00-07-55.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200724000825/Python-2020-07-24-00-07-55.mp4)</video>