# PYqt5 QDockWidget–设置垂直标题栏

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-设置-垂直-标题栏/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-vertical-title-bar/)

在本文中，我们将看到如何为 QDockWidget 设置垂直标题栏。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。默认情况下，标题栏是水平的，尽管我们可以随时使它垂直。

> 为此，我们将对 dock widget 对象使用`setFeatures`方法。
> 
> **语法:**dock . set features(qdlock widget)。dockwidgetverticaltitlebar)
> 
> **自变量:**以垂直特征对象为自变量
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
        dock.setWindowTitle("GfG Title")

        # creating a QWidget object
        widget = QWidget(self)

        # creating a vertical box layout
        layout = QVBoxLayout(self)

        # push button 1
        push1 = QPushButton("A", self)

        # push button 2
        push2 = QPushButton("B", self)

        # adding these buttons to the layout
        layout.addWidget(push1)
        layout.addWidget(push2)

        # setting the layout to the widget
        widget.setLayout(layout)

        # adding widget to the layout
        dock.setWidget(widget)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # setting vertical title bar
        dock.setFeatures(QDockWidget.DockWidgetVerticalTitleBar)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-460010-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726011316/Python-2020-07-26-01-11-27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200726011316/Python-2020-07-26-01-11-27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726011316/Python-2020-07-26-01-11-27.mp4)</video>