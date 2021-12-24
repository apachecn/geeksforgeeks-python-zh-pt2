# PYqt5 QDockWidget–允许区域改变信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-允许-区域-已更改-信号/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-allowed-area-changed-signal/)

在本文中，我们将看到如何允许 QDockWidget 的区域变化信号。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。Dock 可以在主窗口的任何地方移动，设置 dock widget 可以放置的允许区域，可以借助`setAllowedAreas`方法进行设置。当允许的停靠区域发生变化时，会发出此信号。

> 为此，我们将对 dock widget 对象使用`allowedAreasChanged`方法。
> 
> **语法:**dock . allowedareas changed . connect(方法)
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

        # getting allowed area change signal
        # setting text to the label
        dock.allowedAreasChanged.connect(lambda: label.setText("Allowed Area is changed"))

        # setting allowed area
        dock.setAllowedAreas(Qt.LeftDockWidgetArea)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0830fa5caa2823f7022589d1f4e04688.png)