# PYqt5 QDockWidget–码头位置改变信号

> 原文:[https://www . geesforgeks . org/pyqt 5-qdock widget-dock-location-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-dock-location-changed-signal/)

在这篇文章中，我们将看到如何获得 QDockWidget 的停靠位置改变信号。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。
当 dock widget 移动到另一个 dock 区域，或者移动到其当前 dock 区域的不同位置时，会发出此信号。当用户以编程方式移动 dock 小部件或将其拖到新位置时，就会发生这种情况。

> 为此，我们将对 dock widget 对象使用`dockLocationChanged`方法。
> 
> **语法:**dock . docklocationchanged . connect(方法)
> 
> **自变量:**以方法为自变量
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

        dock.setAllowedAreas(Qt.NoDockWidgetArea)

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

        # getting dock location changed signal
        # setting text to the label
        dock.dockLocationChanged.connect(lambda: label.setText("Dock Location Changed Signal Emitted"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6b59323a4e9f0ca8e8109b3d1b801644.png)