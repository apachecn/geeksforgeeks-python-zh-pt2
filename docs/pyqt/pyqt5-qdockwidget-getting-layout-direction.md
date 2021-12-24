# PyQt5 qdockewidget–获取布局方向

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-layout-direction/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-layout-direction/)

在本文中，我们将看到如何获得 QDockWidget 的布局方向。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。布局指定孩子如何排列，通过设置布局方向我们可以指定排列的顺序，可以借助`setLayoutDirection`方法进行设置。

> 为此，我们将对 dock widget 对象使用`layoutDirection`方法。
> 
> **语法:** dock.layoutDirection()
> 
> **论证:**不需要论证
> 
> **返回:**返回方向对象

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
![](img/2813cc26e7887d4358b1ef3cad141de9.png)