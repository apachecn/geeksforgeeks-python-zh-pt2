# PYqt5 QDockWidget–获取标题栏小工具

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-title-bar-widget/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-title-bar-widget/)

在本文中，我们将看到如何获得 QDockWidget 的标题栏小部件。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。标题栏小部件是由标题及其可用选项组成的小部件，尽管我们可以借助`setTitleBarWidget`方法随时更改它。

> 为此，我们将对 dock widget 对象使用`titleBarWidget`方法。
> 
> **语法:**dock . titlebargesetz()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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
        dock.setWindowTitle("                   GfG ")

        # push button
        push = QPushButton("Press", self)

        # setting widget to the dock
        dock.setWidget(push)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # creating a label
        widget = QLabel("Geeks", self)

        # setting title bar widget to the dock
        dock.setTitleBarWidget(widget)

        # getting title bar widget
        value = dock.titleBarWidget()

        # setting text to the label
        label.setText("Title Bar widget : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0ec9a69cce67a4e23ca568109c3b7d23.png)