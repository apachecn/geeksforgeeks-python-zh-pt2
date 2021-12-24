# PYqt5 QDockWidget–取消设置布局方向

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-unset-layout-direction/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-unsetting-layout-direction/)

在本文中，我们将看到如何取消 QDockWidget 的布局方向。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。布局指定孩子如何排列，通过设置布局方向我们可以指定排列的顺序，可以借助`setLayoutDirection`方法进行设置。取消设置意味着布局方向将恢复为默认方向。

> 为此，我们将对 dock widget 对象使用`unsetLayoutDirection`方法。
> 
> **语法:** dock.unsetLayoutDirection()
> 
> **论证:**不需要论证
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
        dock.setWindowTitle("                   GfG ")

        # push button
        push = QPushButton("Press", self)

        # setting widget to the dock
        dock.setWidget(push)

        # setting layout direction
        dock.setLayoutDirection(Qt.RightToLeft)

        # unsetting layout direction
        dock.unsetLayoutDirection()

        # creating a label
        label = QLabel("GfG", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # getting layout direction of dock
        value = dock.layoutDirection()

        # setting text to the label
        label.setText("Layout Direction : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/60be91911a25304c6d5fdf8a36b93aad.png)